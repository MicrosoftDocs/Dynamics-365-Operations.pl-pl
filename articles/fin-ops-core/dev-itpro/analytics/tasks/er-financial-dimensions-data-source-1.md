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
ms.openlocfilehash: ca295d651838f34106c9b91a53efc1f4faad4e4a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182492"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1-design-data-model"></a><span data-ttu-id="1b8bd-103">ER Używanie wymiarów finansowych jako źródła danych (Część 1: Projektowanie modelu danych)</span><span class="sxs-lookup"><span data-stu-id="1b8bd-103">ER Use financial dimensions as a data source (Part 1: Design data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1b8bd-104">W poniższych krokach wyjaśniono, jak administrator systemu lub deweloper raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="1b8bd-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="1b8bd-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-106">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="1b8bd-107">Tworzenie nowego modelu danych</span><span class="sxs-lookup"><span data-stu-id="1b8bd-107">Create a new data model</span></span>
1. <span data-ttu-id="1b8bd-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="1b8bd-109">Upewnij się, że dostawca „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="1b8bd-109">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="1b8bd-110">jest dostępny i oznaczony jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="1b8bd-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="1b8bd-112">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="1b8bd-113">W polu Nazwa wpisz „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="1b8bd-114">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-114">Click Create configuration.</span></span>
6. <span data-ttu-id="1b8bd-115">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-115">Click Designer.</span></span>
7. <span data-ttu-id="1b8bd-116">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="1b8bd-117">W polu Nazwa wpisz „Wpis”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="1b8bd-118">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-118">Click Add.</span></span>
10. <span data-ttu-id="1b8bd-119">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="1b8bd-120">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="1b8bd-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-121">Click Add.</span></span>
    * <span data-ttu-id="1b8bd-122">Do naszego modelu dodamy nową listę rekordów.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-122">We will add to our model a new record list.</span></span> <span data-ttu-id="1b8bd-123">Ta lista będzie udostępniać (dla wszystkich raportów raportowania elektronicznego używających tego modelu jako źródła danych) ustawienia wybranych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="1b8bd-124">Każdy wymiar finansowy będzie wyświetlany na tej liście jako rekord z odpowiednimi polami reprezentującymi ustawienie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s setting.</span></span>  
13. <span data-ttu-id="1b8bd-125">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="1b8bd-126">W polu Nazwa wpisz „Ustawienie wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="1b8bd-127">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="1b8bd-128">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-128">Click Add.</span></span>
17. <span data-ttu-id="1b8bd-129">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="1b8bd-130">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="1b8bd-131">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="1b8bd-132">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-132">Click Add.</span></span>
21. <span data-ttu-id="1b8bd-133">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="1b8bd-134">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="1b8bd-135">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-135">Click Add.</span></span>
24. <span data-ttu-id="1b8bd-136">W drzewie wybierz pozycję „Wpis”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="1b8bd-137">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="1b8bd-138">W polu Nazwa wpisz „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="1b8bd-139">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="1b8bd-140">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-140">Click Add.</span></span>
29. <span data-ttu-id="1b8bd-141">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="1b8bd-142">W polu Nazwa wpisz „Partia”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="1b8bd-143">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="1b8bd-144">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-144">Click Add.</span></span>
33. <span data-ttu-id="1b8bd-145">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="1b8bd-146">W polu Nazwa wpisz „Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="1b8bd-147">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="1b8bd-148">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-148">Click Add.</span></span>
37. <span data-ttu-id="1b8bd-149">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="1b8bd-150">W polu Nazwa wpisz „Data”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="1b8bd-151">W polu Typ elementu wybierz opcję „Data”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="1b8bd-152">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-152">Click Add.</span></span>
41. <span data-ttu-id="1b8bd-153">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="1b8bd-154">W polu Nazwa wpisz „Debet”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="1b8bd-155">W polu Typ elementu wybierz opcję „Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="1b8bd-156">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-156">Click Add.</span></span>
45. <span data-ttu-id="1b8bd-157">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="1b8bd-158">W polu Nazwa wpisz „Kredyt”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="1b8bd-159">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-159">Click Add.</span></span>
48. <span data-ttu-id="1b8bd-160">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="1b8bd-161">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="1b8bd-162">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="1b8bd-163">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-163">Click Add.</span></span>
52. <span data-ttu-id="1b8bd-164">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="1b8bd-165">W polu Nazwa wpisz „Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="1b8bd-166">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-166">Click Add.</span></span>
55. <span data-ttu-id="1b8bd-167">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="1b8bd-168">W polu Nazwa wpisz „Dane wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="1b8bd-169">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="1b8bd-170">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-170">Click Add.</span></span>
    * <span data-ttu-id="1b8bd-171">Do naszego modelu dodaliśmy nową listę rekordów.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-171">We added to our model a new record list.</span></span> <span data-ttu-id="1b8bd-172">Ta lista będzie udostępniać (dla wszystkich raportów raportowania elektronicznego używających tego modelu jako źródła danych) wartości wybranych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="1b8bd-173">Każdy wymiar finansowy będzie wyświetlany na tej liście jako rekord z odpowiednimi polami reprezentującymi wartości wymiaru.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s values.</span></span> <span data-ttu-id="1b8bd-174">Nazwa wymiaru będzie również przedstawiana w tym rekordzie jako pole, które w razie potrzeby ma być używane na potrzeby wybierania.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="1b8bd-175">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="1b8bd-176">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="1b8bd-177">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="1b8bd-178">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-178">Click Add.</span></span>
63. <span data-ttu-id="1b8bd-179">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="1b8bd-180">W polu Nazwa wpisz „Opis”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="1b8bd-181">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-181">Click Add.</span></span>
66. <span data-ttu-id="1b8bd-182">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="1b8bd-183">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="1b8bd-184">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-184">Click Add.</span></span>
69. <span data-ttu-id="1b8bd-185">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-185">Click Save.</span></span>
70. <span data-ttu-id="1b8bd-186">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1b8bd-186">Close the page.</span></span>

