---
title: ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 2 — Konfigurowanie obliczeń)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d785b321037645837dbcbaf28c8ede9b8e97b79
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550609"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a><span data-ttu-id="9523c-103">ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 2 — Konfigurowanie obliczeń)</span><span class="sxs-lookup"><span data-stu-id="9523c-103">ER Configure format to do counting and summing (Part 2 - Configure computations)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9523c-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="9523c-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="9523c-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="9523c-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="9523c-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 1: Tworzenie formatu)”.</span><span class="sxs-lookup"><span data-stu-id="9523c-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 1: Create format)” procedure.</span></span>

<span data-ttu-id="9523c-107">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="9523c-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a><span data-ttu-id="9523c-108">Tworzenie konfiguracji formatu w celu dodania szczegółów inwentaryzacji i sumowania</span><span class="sxs-lookup"><span data-stu-id="9523c-108">Create a format configuration to add counting and summing details</span></span>
1. <span data-ttu-id="9523c-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="9523c-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9523c-110">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="9523c-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="9523c-111">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="9523c-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="9523c-112">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="9523c-112">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
    * <span data-ttu-id="9523c-113">Załóżmy, że trzeba dostosować format dostarczony przez firmę Microsoft, dodając wiersze zawierające szczegóły podsumowania na końcu raportu Intrastat.</span><span class="sxs-lookup"><span data-stu-id="9523c-113">Assume that you need to customize the format provided by Microsoft by adding lines with summary details at the end of the Intrastat report.</span></span> <span data-ttu-id="9523c-114">Należy to zrobić poprzez utworzenie własnej pochodnej konfiguracji Intrastat na podstawie wystąpienia otrzymanego od Microsoft i w niej wprowadzić modyfikacje.</span><span class="sxs-lookup"><span data-stu-id="9523c-114">You need to do that by deriving our own instance of the Intrastat configuration from the Microsoft instance to make modifications.</span></span>  
5. <span data-ttu-id="9523c-115">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9523c-115">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="9523c-116">W polu Nowy wprowadź wyrażenie „Pochodzi od nazwy: Intrastat (Niemcy), Microsoft”.</span><span class="sxs-lookup"><span data-stu-id="9523c-116">In the New field, enter 'Derive from Name: Intrastat (DE), Microsoft'.</span></span>
7. <span data-ttu-id="9523c-117">W polu Nazwa wpisz wyrażenie „Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="9523c-117">In the Name field, type 'Intrastat (DE) with counting & summing'.</span></span>
8. <span data-ttu-id="9523c-118">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="9523c-118">Click Create configuration.</span></span>

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a><span data-ttu-id="9523c-119">Konfigurowanie tego raportu w celu wykonania inwentaryzacji i sumowania na podstawie szczegółów danych wyjściowych</span><span class="sxs-lookup"><span data-stu-id="9523c-119">Configure this report to do counting and summation based on output details</span></span>
1. <span data-ttu-id="9523c-120">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="9523c-120">Click Designer.</span></span>
2. <span data-ttu-id="9523c-121">W polu Pobierz szczegóły rezultatu zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="9523c-121">Select Yes in the Collect output details field.</span></span>
    * <span data-ttu-id="9523c-122">Ta flaga będzie w czasie wykonywania uaktywniać proces gromadzenia szczegółów wyjściowych w celu wygenerowania pliku Intrastat.</span><span class="sxs-lookup"><span data-stu-id="9523c-122">This flag will activate at run-time the process of collecting output details for generating the Intrastat file.</span></span>  
    * <span data-ttu-id="9523c-123">Musisz wykonać inwentaryzację dla różnych kierunków Intrastat, dlatego dodasz dedykowane wyliczenie modelu do tej konfiguracji formatu używanej przez listę źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="9523c-123">You need to do counting for different Intrastat directions, so add a dedicated model enumeration to the data sources’ list of this format configuration.</span></span>  
3. <span data-ttu-id="9523c-124">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="9523c-124">Click the Mapping tab.</span></span>
4. <span data-ttu-id="9523c-125">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9523c-125">Click Add root to open the drop dialog.</span></span>
5. <span data-ttu-id="9523c-126">W drzewie zaznacz element „Model danych\Wyliczenie”.</span><span class="sxs-lookup"><span data-stu-id="9523c-126">In the tree, select 'Data model\Enumeration '.</span></span>
6. <span data-ttu-id="9523c-127">W polu Nazwa wpisz „Kierunek”.</span><span class="sxs-lookup"><span data-stu-id="9523c-127">In the Name field, type 'Direction'.</span></span>
7. <span data-ttu-id="9523c-128">W polu Wyliczenie modeli wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="9523c-128">In the Model enumeration field, enter or select a value.</span></span>
    * <span data-ttu-id="9523c-129">Wybierz wartość Kierunek.</span><span class="sxs-lookup"><span data-stu-id="9523c-129">Select the value Direction.</span></span>  
8. <span data-ttu-id="9523c-130">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9523c-130">Click OK.</span></span>
9. <span data-ttu-id="9523c-131">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9523c-131">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="9523c-132">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="9523c-132">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="9523c-133">W polu Nazwa wpisz „$BlockName”.</span><span class="sxs-lookup"><span data-stu-id="9523c-133">In the Name field, type '$BlockName'.</span></span>
12. <span data-ttu-id="9523c-134">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="9523c-134">Click Edit formula.</span></span>
13. <span data-ttu-id="9523c-135">W polu Formuła wpisz „blok”.</span><span class="sxs-lookup"><span data-stu-id="9523c-135">In the Formula field, enter '"block"'.</span></span>
14. <span data-ttu-id="9523c-136">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-136">Click Save.</span></span>
15. <span data-ttu-id="9523c-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-137">Close the page.</span></span>
16. <span data-ttu-id="9523c-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9523c-138">Click OK.</span></span>
17. <span data-ttu-id="9523c-139">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9523c-139">Click Add root to open the drop dialog.</span></span>
18. <span data-ttu-id="9523c-140">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="9523c-140">In the tree, select 'Functions\Calculated field'.</span></span>
19. <span data-ttu-id="9523c-141">W polu Nazwa wpisz „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="9523c-141">In the Name field, type '$RecName'.</span></span>
20. <span data-ttu-id="9523c-142">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="9523c-142">Click Edit formula.</span></span>
21. <span data-ttu-id="9523c-143">W polu Formuła wpisz „rekord”.</span><span class="sxs-lookup"><span data-stu-id="9523c-143">In the Formula field, enter '"record"'.</span></span>
22. <span data-ttu-id="9523c-144">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-144">Click Save.</span></span>
23. <span data-ttu-id="9523c-145">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-145">Close the page.</span></span>
24. <span data-ttu-id="9523c-146">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9523c-146">Click OK.</span></span>
25. <span data-ttu-id="9523c-147">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9523c-147">Click Add root to open the drop dialog.</span></span>
26. <span data-ttu-id="9523c-148">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="9523c-148">In the tree, select 'Functions\Calculated field'.</span></span>
27. <span data-ttu-id="9523c-149">W polu Nazwa wpisz „$InvName”.</span><span class="sxs-lookup"><span data-stu-id="9523c-149">In the Name field, type '$InvName'.</span></span>
28. <span data-ttu-id="9523c-150">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="9523c-150">Click Edit formula.</span></span>
29. <span data-ttu-id="9523c-151">W polu Formuła wpisz „InvoicedAmountEUR”.</span><span class="sxs-lookup"><span data-stu-id="9523c-151">In the Formula field, enter '"InvoicedAmountEUR"'.</span></span>
30. <span data-ttu-id="9523c-152">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-152">Click Save.</span></span>
31. <span data-ttu-id="9523c-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-153">Close the page.</span></span>
32. <span data-ttu-id="9523c-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9523c-154">Click OK.</span></span>
33. <span data-ttu-id="9523c-155">W drzewie zaznacz element „Intrastat\Dane”.</span><span class="sxs-lookup"><span data-stu-id="9523c-155">In the tree, select 'Intrastat\Data'.</span></span>
34. <span data-ttu-id="9523c-156">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="9523c-156">Click Edit button for the ‘Collected data key name’ field</span></span>
35. <span data-ttu-id="9523c-157">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="9523c-157">Click Add data source.</span></span>
    * <span data-ttu-id="9523c-158">$BlockName</span><span class="sxs-lookup"><span data-stu-id="9523c-158">$BlockName</span></span>  
36. <span data-ttu-id="9523c-159">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-159">Click Save.</span></span>
37. <span data-ttu-id="9523c-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-160">Close the page.</span></span>
38. <span data-ttu-id="9523c-161">Kliknij przycisk Edytuj obok pola Wartość pobranego klucza danych.</span><span class="sxs-lookup"><span data-stu-id="9523c-161">Click the Edit button for the Collected data key value field.</span></span>
39. <span data-ttu-id="9523c-162">W polu Formuła wpisz wyrażenie „IF(Intrastat.CommodityRecord.Direction=Kierunek.Import, "Import", "Eksport")”.</span><span class="sxs-lookup"><span data-stu-id="9523c-162">In the Formula field, enter 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.</span></span>
    * <span data-ttu-id="9523c-163">IF(Intrastat.CommodityRecord.Direction=Kierunek.Import, "Import", "Eksport")</span><span class="sxs-lookup"><span data-stu-id="9523c-163">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span></span>  
40. <span data-ttu-id="9523c-164">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-164">Click Save.</span></span>
41. <span data-ttu-id="9523c-165">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-165">Close the page.</span></span>
    * <span data-ttu-id="9523c-166">Liczenie wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="9523c-166">Count the lines of this sequence.</span></span> <span data-ttu-id="9523c-167">Wyniki zostaną użyte z nazwą „blok” oddzielnie dla różnych kierunków.</span><span class="sxs-lookup"><span data-stu-id="9523c-167">The results will be used with the name “block” separately for different directions.</span></span> <span data-ttu-id="9523c-168">Wartość „Import” będzie używana dla wszelkich transakcji Intrastat przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="9523c-168">Value “Import” will be used for any arrivals Intrastat transactions.</span></span> <span data-ttu-id="9523c-169">Wartość „Eksport” będzie używana dla wszelkich transakcji Intrastat wysyłki.</span><span class="sxs-lookup"><span data-stu-id="9523c-169">The value “Export” will be used for any Intrastat dispatches transactions.</span></span> <span data-ttu-id="9523c-170">Potraktuj to jako wirtualny arkusz kalkulacyjny programu Excel.</span><span class="sxs-lookup"><span data-stu-id="9523c-170">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="9523c-171">Dla każdej transakcji będzie tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”.</span><span class="sxs-lookup"><span data-stu-id="9523c-171">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly.</span></span>  
42. <span data-ttu-id="9523c-172">W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja”.</span><span class="sxs-lookup"><span data-stu-id="9523c-172">In the tree, expand 'Intrastat\Data: Sequence'.</span></span>
43. <span data-ttu-id="9523c-173">W drzewie zaznacz element „Intrastat\Dane: Sekwencja\Przyjęcia?”.</span><span class="sxs-lookup"><span data-stu-id="9523c-173">In the tree, select 'Intrastat\Data: Sequence\Arrivals?'.</span></span>
44. <span data-ttu-id="9523c-174">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="9523c-174">Click Edit button for the ‘Collected data key name’ field.</span></span>
    * <span data-ttu-id="9523c-175">Liczenie wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="9523c-175">Count the lines of this sequence.</span></span> <span data-ttu-id="9523c-176">Wyniki zostaną zapamiętane pod nazwą „rekord”.</span><span class="sxs-lookup"><span data-stu-id="9523c-176">The results will be memorized using the name “record”.</span></span>  
45. <span data-ttu-id="9523c-177">W drzewie zaznacz element „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="9523c-177">In the tree, select '$RecName'.</span></span>
46. <span data-ttu-id="9523c-178">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="9523c-178">Click Add data source.</span></span>
47. <span data-ttu-id="9523c-179">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-179">Click Save.</span></span>
48. <span data-ttu-id="9523c-180">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-180">Close the page.</span></span>
49. <span data-ttu-id="9523c-181">Kliknij przycisk Edytuj obok pola „Wartość pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="9523c-181">Click Edit button for the ‘Collected data key value’ field</span></span>
50. <span data-ttu-id="9523c-182">W polu Formuła wprowadź wyrażenie „Intrastat.CommodityRecord.CommodityCode”.</span><span class="sxs-lookup"><span data-stu-id="9523c-182">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
51. <span data-ttu-id="9523c-183">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-183">Click Save.</span></span>
52. <span data-ttu-id="9523c-184">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-184">Close the page.</span></span>
    * <span data-ttu-id="9523c-185">Liczenie wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="9523c-185">Count the lines of this sequence.</span></span> <span data-ttu-id="9523c-186">Wyniki zostaną użyte z nazwą „rekord” oddzielnie dla różnych kodów asortymentu.</span><span class="sxs-lookup"><span data-stu-id="9523c-186">The results will be used with the name “record” separately for different commodity codes.</span></span> <span data-ttu-id="9523c-187">Potraktuj to jako wirtualny arkusz kalkulacyjny programu Excel.</span><span class="sxs-lookup"><span data-stu-id="9523c-187">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="9523c-188">Dla każdej transakcji jest tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”, a drugi blok „rekord” jest wypełniany wartością kodu asortymentu.</span><span class="sxs-lookup"><span data-stu-id="9523c-188">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly and the second block “record” is filled with the commodity code value.</span></span>  
53. <span data-ttu-id="9523c-189">W drzewie zaznacz element „Intrastat\Dane: Sekwencja\Wysyłki?”.</span><span class="sxs-lookup"><span data-stu-id="9523c-189">In the tree, select 'Intrastat\Data: Sequence\Dispatches?'.</span></span>
54. <span data-ttu-id="9523c-190">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="9523c-190">Click Edit button for the ‘Collected data key name’ field</span></span>
55. <span data-ttu-id="9523c-191">W drzewie zaznacz element „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="9523c-191">In the tree, select '$RecName'.</span></span>
56. <span data-ttu-id="9523c-192">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="9523c-192">Click Add data source.</span></span>
57. <span data-ttu-id="9523c-193">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-193">Click Save.</span></span>
58. <span data-ttu-id="9523c-194">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-194">Close the page.</span></span>
59. <span data-ttu-id="9523c-195">Kliknij przycisk Edytuj obok pola „Wartość pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="9523c-195">Click the Edit button for the ‘Collected data key value’ field.</span></span>
60. <span data-ttu-id="9523c-196">W polu Formuła wprowadź wyrażenie „Intrastat.CommodityRecord.CommodityCode”.</span><span class="sxs-lookup"><span data-stu-id="9523c-196">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
61. <span data-ttu-id="9523c-197">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-197">Click Save.</span></span>
62. <span data-ttu-id="9523c-198">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-198">Close the page.</span></span>
63. <span data-ttu-id="9523c-199">W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja\Wysyłki: Sekwencja?”.</span><span class="sxs-lookup"><span data-stu-id="9523c-199">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?'.</span></span>
64. <span data-ttu-id="9523c-200">W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja\Wysyłki: Sekwencja?\Rekord = Intrastat.CommodityRecord”.</span><span class="sxs-lookup"><span data-stu-id="9523c-200">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?\Record =  Intrastat.CommodityRecord'.</span></span>
65. <span data-ttu-id="9523c-201">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="9523c-201">Click the Format tab.</span></span>
66. <span data-ttu-id="9523c-202">W drzewie zaznacz element „Intrastat\Dane\Wysyłki\Rekord\Kwota faktury w EUR”.</span><span class="sxs-lookup"><span data-stu-id="9523c-202">In the tree, select 'Intrastat\Data\Dispatches\Record\Invoice amount EUR'.</span></span>
67. <span data-ttu-id="9523c-203">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="9523c-203">Click the Mapping tab.</span></span>
68. <span data-ttu-id="9523c-204">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="9523c-204">Click the Edit button for the ‘Collected data key name’ field.</span></span>
69. <span data-ttu-id="9523c-205">W drzewie zaznacz element „$InvName”.</span><span class="sxs-lookup"><span data-stu-id="9523c-205">In the tree, select '$InvName'.</span></span>
70. <span data-ttu-id="9523c-206">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="9523c-206">Click Add data source.</span></span>
71. <span data-ttu-id="9523c-207">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-207">Click Save.</span></span>
72. <span data-ttu-id="9523c-208">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-208">Close the page.</span></span>
    * <span data-ttu-id="9523c-209">Podsumowanie wartości kwot zafakturowanych dla wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="9523c-209">Summarize the invoiced amount values for lines of this sequence.</span></span> <span data-ttu-id="9523c-210">Wyniki zostaną użyte z nazwą „InvoicedAmountEUR” oddzielnie dla różnych kierunków Intrastat kodów asortymentu.</span><span class="sxs-lookup"><span data-stu-id="9523c-210">The results will be used with the name “InvoicedAmountEUR” separately for different Intrastat directions and commodity codes.</span></span> <span data-ttu-id="9523c-211">Potraktuj to jak tworzenie wirtualnego arkusza kalkulacyjnego w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="9523c-211">Consider this to be a virtual creation in Excel spreadsheet.</span></span> <span data-ttu-id="9523c-212">Dla każdej transakcji będzie tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”.</span><span class="sxs-lookup"><span data-stu-id="9523c-212">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly.</span></span> <span data-ttu-id="9523c-213">Drugi blok „rekord” jest wypełniony wartością kodu asortymentu, a trzecia kolumna „InvoicedAmountEUR” jest wypełniona wartością kwoty faktury.</span><span class="sxs-lookup"><span data-stu-id="9523c-213">The second block “record” is filled with the commodity code value, and the third column “InvoicedAmountEUR” is filled with the invoice amount value.</span></span>  
73. <span data-ttu-id="9523c-214">W drzewie rozwiń węzeł „Intrastat\Dane\Przyjęcia?”.</span><span class="sxs-lookup"><span data-stu-id="9523c-214">In the tree, expand 'Intrastat\Data\Arrivals?'.</span></span>
74. <span data-ttu-id="9523c-215">W drzewie rozwiń węzeł „Intrastat\Dane\Przyjęcia?\Rekord = Intrastat.CommodityRecord”.</span><span class="sxs-lookup"><span data-stu-id="9523c-215">In the tree, expand 'Intrastat\Data\Arrivals?\Record =  Intrastat.CommodityRecord'.</span></span>
75. <span data-ttu-id="9523c-216">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="9523c-216">Click the Format tab.</span></span>
76. <span data-ttu-id="9523c-217">W drzewie zaznacz element „Intrastat\Dane\Przyjęcia\Rekord\Kwota faktury w EUR”.</span><span class="sxs-lookup"><span data-stu-id="9523c-217">In the tree, select 'Intrastat\Data\Arrivals\Record\Invoice amount EUR'.</span></span>
77. <span data-ttu-id="9523c-218">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="9523c-218">Click the Mapping tab.</span></span>
78. <span data-ttu-id="9523c-219">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="9523c-219">Click the Edit button for the ‘Collected data key name’ field.</span></span>
79. <span data-ttu-id="9523c-220">W drzewie zaznacz element „$InvName”.</span><span class="sxs-lookup"><span data-stu-id="9523c-220">In the tree, select '$InvName'.</span></span>
80. <span data-ttu-id="9523c-221">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="9523c-221">Click Add data source.</span></span>
81. <span data-ttu-id="9523c-222">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-222">Click Save.</span></span>
82. <span data-ttu-id="9523c-223">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-223">Close the page.</span></span>
83. <span data-ttu-id="9523c-224">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9523c-224">Click Save.</span></span>
84. <span data-ttu-id="9523c-225">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9523c-225">Close the page.</span></span>

