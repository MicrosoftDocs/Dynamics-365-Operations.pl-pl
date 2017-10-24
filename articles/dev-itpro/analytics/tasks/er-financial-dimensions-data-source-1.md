--- 
title: "Projektowanie modelu danych w celu używania wymiarów finansowych jako źródła danych na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak administrator systemu lub deweloper raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER."
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: d8a03c4b85666975a7b42d46f3afdd35019e9b93
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="design-data-model-to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="dd434-103">Projektowanie modelu danych w celu używania wymiarów finansowych jako źródła danych na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="dd434-103">Design data model to use financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dd434-104">W poniższych krokach wyjaśniono, jak administrator systemu lub deweloper raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="dd434-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="dd434-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="dd434-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="dd434-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="dd434-106">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="dd434-107">Tworzenie nowego modelu danych</span><span class="sxs-lookup"><span data-stu-id="dd434-107">Create a new data model</span></span>
1. <span data-ttu-id="dd434-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="dd434-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="dd434-109">Upewnij się, że dostawca „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="dd434-109">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="dd434-110">jest dostępny i oznaczony jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="dd434-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="dd434-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="dd434-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="dd434-112">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="dd434-113">W polu Nazwa wpisz „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="dd434-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="dd434-114">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="dd434-114">Click Create configuration.</span></span>
6. <span data-ttu-id="dd434-115">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="dd434-115">Click Designer.</span></span>
7. <span data-ttu-id="dd434-116">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="dd434-117">W polu Nazwa wpisz „Wpis”.</span><span class="sxs-lookup"><span data-stu-id="dd434-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="dd434-118">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-118">Click Add.</span></span>
10. <span data-ttu-id="dd434-119">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="dd434-120">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="dd434-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="dd434-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-121">Click Add.</span></span>
    * <span data-ttu-id="dd434-122">Do naszego modelu dodamy nową listę rekordów.</span><span class="sxs-lookup"><span data-stu-id="dd434-122">We will add to our model a new record list.</span></span> <span data-ttu-id="dd434-123">Ta lista będzie udostępniać (dla wszystkich raportów raportowania elektronicznego używających tego modelu jako źródła danych) ustawienia wybranych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="dd434-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="dd434-124">Każdy wymiar finansowy będzie wyświetlany na tej liście jako rekord z odpowiednimi polami reprezentującymi ustawienie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="dd434-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s setting.</span></span>  
13. <span data-ttu-id="dd434-125">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="dd434-126">W polu Nazwa wpisz „Ustawienie wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="dd434-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="dd434-127">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="dd434-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="dd434-128">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-128">Click Add.</span></span>
17. <span data-ttu-id="dd434-129">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="dd434-130">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="dd434-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="dd434-131">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="dd434-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="dd434-132">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-132">Click Add.</span></span>
21. <span data-ttu-id="dd434-133">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="dd434-134">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="dd434-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="dd434-135">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-135">Click Add.</span></span>
24. <span data-ttu-id="dd434-136">W drzewie wybierz pozycję „Wpis”.</span><span class="sxs-lookup"><span data-stu-id="dd434-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="dd434-137">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="dd434-138">W polu Nazwa wpisz „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="dd434-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="dd434-139">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="dd434-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="dd434-140">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-140">Click Add.</span></span>
29. <span data-ttu-id="dd434-141">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="dd434-142">W polu Nazwa wpisz „Partia”.</span><span class="sxs-lookup"><span data-stu-id="dd434-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="dd434-143">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="dd434-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="dd434-144">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-144">Click Add.</span></span>
33. <span data-ttu-id="dd434-145">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="dd434-146">W polu Nazwa wpisz „Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="dd434-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="dd434-147">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="dd434-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="dd434-148">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-148">Click Add.</span></span>
37. <span data-ttu-id="dd434-149">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="dd434-150">W polu Nazwa wpisz „Data”.</span><span class="sxs-lookup"><span data-stu-id="dd434-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="dd434-151">W polu Typ elementu wybierz opcję „Data”.</span><span class="sxs-lookup"><span data-stu-id="dd434-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="dd434-152">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-152">Click Add.</span></span>
41. <span data-ttu-id="dd434-153">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="dd434-154">W polu Nazwa wpisz „Debet”.</span><span class="sxs-lookup"><span data-stu-id="dd434-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="dd434-155">W polu Typ elementu wybierz opcję „Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="dd434-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="dd434-156">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-156">Click Add.</span></span>
45. <span data-ttu-id="dd434-157">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="dd434-158">W polu Nazwa wpisz „Kredyt”.</span><span class="sxs-lookup"><span data-stu-id="dd434-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="dd434-159">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-159">Click Add.</span></span>
48. <span data-ttu-id="dd434-160">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="dd434-161">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="dd434-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="dd434-162">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="dd434-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="dd434-163">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-163">Click Add.</span></span>
52. <span data-ttu-id="dd434-164">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="dd434-165">W polu Nazwa wpisz „Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="dd434-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="dd434-166">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-166">Click Add.</span></span>
55. <span data-ttu-id="dd434-167">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="dd434-168">W polu Nazwa wpisz „Dane wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="dd434-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="dd434-169">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="dd434-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="dd434-170">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-170">Click Add.</span></span>
    * <span data-ttu-id="dd434-171">Do naszego modelu dodaliśmy nową listę rekordów.</span><span class="sxs-lookup"><span data-stu-id="dd434-171">We added to our model a new record list.</span></span> <span data-ttu-id="dd434-172">Ta lista będzie udostępniać (dla wszystkich raportów raportowania elektronicznego używających tego modelu jako źródła danych) wartości wybranych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="dd434-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="dd434-173">Każdy wymiar finansowy będzie wyświetlany na tej liście jako rekord z odpowiednimi polami reprezentującymi wartości wymiaru.</span><span class="sxs-lookup"><span data-stu-id="dd434-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s values.</span></span> <span data-ttu-id="dd434-174">Nazwa wymiaru będzie również przedstawiana w tym rekordzie jako pole, które w razie potrzeby ma być używane na potrzeby wybierania.</span><span class="sxs-lookup"><span data-stu-id="dd434-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="dd434-175">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="dd434-176">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="dd434-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="dd434-177">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="dd434-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="dd434-178">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-178">Click Add.</span></span>
63. <span data-ttu-id="dd434-179">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="dd434-180">W polu Nazwa wpisz „Opis”.</span><span class="sxs-lookup"><span data-stu-id="dd434-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="dd434-181">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-181">Click Add.</span></span>
66. <span data-ttu-id="dd434-182">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd434-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="dd434-183">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="dd434-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="dd434-184">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dd434-184">Click Add.</span></span>
69. <span data-ttu-id="dd434-185">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dd434-185">Click Save.</span></span>
70. <span data-ttu-id="dd434-186">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dd434-186">Close the page.</span></span>


