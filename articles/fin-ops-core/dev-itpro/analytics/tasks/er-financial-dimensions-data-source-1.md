---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 1 — Projektowanie modelu danych)
description: W poniższych krokach wyjaśniono, jak administrator systemu lub deweloper raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b02496ebb06e0c2eb644fc7ef3280ca4eca05923
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142042"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a><span data-ttu-id="34c18-103">ER Używanie wymiarów finansowych jako źródła danych (Część 1 — Projektowanie modelu danych)</span><span class="sxs-lookup"><span data-stu-id="34c18-103">ER Use financial dimensions as a data source (Part 1 - Design data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="34c18-104">W poniższych krokach wyjaśniono, jak administrator systemu lub deweloper raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="34c18-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="34c18-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="34c18-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="34c18-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="34c18-106">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="34c18-107">Tworzenie nowego modelu danych</span><span class="sxs-lookup"><span data-stu-id="34c18-107">Create a new data model</span></span>
1. <span data-ttu-id="34c18-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="34c18-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="34c18-109">Upewnij się, że dostawca „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="34c18-109">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="34c18-110">jest dostępny i oznaczony jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="34c18-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="34c18-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="34c18-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="34c18-112">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="34c18-113">W polu Nazwa wpisz „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="34c18-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="34c18-114">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="34c18-114">Click Create configuration.</span></span>
6. <span data-ttu-id="34c18-115">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="34c18-115">Click Designer.</span></span>
7. <span data-ttu-id="34c18-116">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="34c18-117">W polu Nazwa wpisz „Wpis”.</span><span class="sxs-lookup"><span data-stu-id="34c18-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="34c18-118">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-118">Click Add.</span></span>
10. <span data-ttu-id="34c18-119">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="34c18-120">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="34c18-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="34c18-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-121">Click Add.</span></span>
    * <span data-ttu-id="34c18-122">Do naszego modelu dodamy nową listę rekordów.</span><span class="sxs-lookup"><span data-stu-id="34c18-122">We will add to our model a new record list.</span></span> <span data-ttu-id="34c18-123">Ta lista będzie udostępniać (dla wszystkich raportów raportowania elektronicznego używających tego modelu jako źródła danych) ustawienia wybranych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="34c18-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="34c18-124">Każdy wymiar finansowy będzie wyświetlany na tej liście jako rekord z odpowiednimi polami reprezentującymi ustawienie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="34c18-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's setting.</span></span>  
13. <span data-ttu-id="34c18-125">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="34c18-126">W polu Nazwa wpisz „Ustawienie wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="34c18-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="34c18-127">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="34c18-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="34c18-128">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-128">Click Add.</span></span>
17. <span data-ttu-id="34c18-129">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="34c18-130">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="34c18-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="34c18-131">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="34c18-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="34c18-132">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-132">Click Add.</span></span>
21. <span data-ttu-id="34c18-133">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="34c18-134">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="34c18-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="34c18-135">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-135">Click Add.</span></span>
24. <span data-ttu-id="34c18-136">W drzewie wybierz pozycję „Wpis”.</span><span class="sxs-lookup"><span data-stu-id="34c18-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="34c18-137">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="34c18-138">W polu Nazwa wpisz „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="34c18-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="34c18-139">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="34c18-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="34c18-140">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-140">Click Add.</span></span>
29. <span data-ttu-id="34c18-141">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="34c18-142">W polu Nazwa wpisz „Partia”.</span><span class="sxs-lookup"><span data-stu-id="34c18-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="34c18-143">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="34c18-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="34c18-144">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-144">Click Add.</span></span>
33. <span data-ttu-id="34c18-145">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="34c18-146">W polu Nazwa wpisz „Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="34c18-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="34c18-147">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="34c18-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="34c18-148">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-148">Click Add.</span></span>
37. <span data-ttu-id="34c18-149">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="34c18-150">W polu Nazwa wpisz „Data”.</span><span class="sxs-lookup"><span data-stu-id="34c18-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="34c18-151">W polu Typ elementu wybierz opcję „Data”.</span><span class="sxs-lookup"><span data-stu-id="34c18-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="34c18-152">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-152">Click Add.</span></span>
41. <span data-ttu-id="34c18-153">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="34c18-154">W polu Nazwa wpisz „Debet”.</span><span class="sxs-lookup"><span data-stu-id="34c18-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="34c18-155">W polu Typ elementu wybierz opcję „Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="34c18-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="34c18-156">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-156">Click Add.</span></span>
45. <span data-ttu-id="34c18-157">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="34c18-158">W polu Nazwa wpisz „Kredyt”.</span><span class="sxs-lookup"><span data-stu-id="34c18-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="34c18-159">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-159">Click Add.</span></span>
48. <span data-ttu-id="34c18-160">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="34c18-161">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="34c18-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="34c18-162">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="34c18-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="34c18-163">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-163">Click Add.</span></span>
52. <span data-ttu-id="34c18-164">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="34c18-165">W polu Nazwa wpisz „Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="34c18-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="34c18-166">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-166">Click Add.</span></span>
55. <span data-ttu-id="34c18-167">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="34c18-168">W polu Nazwa wpisz „Dane wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="34c18-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="34c18-169">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="34c18-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="34c18-170">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-170">Click Add.</span></span>
    * <span data-ttu-id="34c18-171">Do naszego modelu dodaliśmy nową listę rekordów.</span><span class="sxs-lookup"><span data-stu-id="34c18-171">We added to our model a new record list.</span></span> <span data-ttu-id="34c18-172">Ta lista będzie udostępniać (dla wszystkich raportów raportowania elektronicznego używających tego modelu jako źródła danych) wartości wybranych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="34c18-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="34c18-173">Każdy wymiar finansowy będzie wyświetlany na tej liście jako rekord z odpowiednimi polami reprezentującymi wartości wymiaru.</span><span class="sxs-lookup"><span data-stu-id="34c18-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's values.</span></span> <span data-ttu-id="34c18-174">Nazwa wymiaru będzie również przedstawiana w tym rekordzie jako pole, które w razie potrzeby ma być używane na potrzeby wybierania.</span><span class="sxs-lookup"><span data-stu-id="34c18-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="34c18-175">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="34c18-176">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="34c18-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="34c18-177">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="34c18-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="34c18-178">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-178">Click Add.</span></span>
63. <span data-ttu-id="34c18-179">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="34c18-180">W polu Nazwa wpisz „Opis”.</span><span class="sxs-lookup"><span data-stu-id="34c18-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="34c18-181">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-181">Click Add.</span></span>
66. <span data-ttu-id="34c18-182">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34c18-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="34c18-183">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="34c18-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="34c18-184">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="34c18-184">Click Add.</span></span>
69. <span data-ttu-id="34c18-185">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="34c18-185">Click Save.</span></span>
70. <span data-ttu-id="34c18-186">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="34c18-186">Close the page.</span></span>

