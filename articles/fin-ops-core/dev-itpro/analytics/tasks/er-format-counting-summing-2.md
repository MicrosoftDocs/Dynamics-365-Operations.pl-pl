---
title: ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 2 — Konfigurowanie obliczeń)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego do zliczania i sumowania na podstawie danych już wygenerowanego tekstu wyjściowego. (część 2)
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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6215fe1f32bcb4833bd009b7c33e09edbba17817
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093004"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a><span data-ttu-id="70aec-104">ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 2 — Konfigurowanie obliczeń)</span><span class="sxs-lookup"><span data-stu-id="70aec-104">ER Configure format to do counting and summing (Part 2 - Configure computations)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="70aec-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="70aec-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="70aec-106">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="70aec-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="70aec-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 1: Tworzenie formatu)”.</span><span class="sxs-lookup"><span data-stu-id="70aec-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 1: Create format)" procedure.</span></span>

<span data-ttu-id="70aec-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="70aec-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a><span data-ttu-id="70aec-109">Tworzenie konfiguracji formatu w celu dodania szczegółów inwentaryzacji i sumowania</span><span class="sxs-lookup"><span data-stu-id="70aec-109">Create a format configuration to add counting and summing details</span></span>
1. <span data-ttu-id="70aec-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="70aec-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="70aec-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="70aec-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="70aec-112">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="70aec-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="70aec-113">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="70aec-113">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
    * <span data-ttu-id="70aec-114">Załóżmy, że trzeba dostosować format dostarczony przez firmę Microsoft, dodając wiersze zawierające szczegóły podsumowania na końcu raportu Intrastat.</span><span class="sxs-lookup"><span data-stu-id="70aec-114">Assume that you need to customize the format provided by Microsoft by adding lines with summary details at the end of the Intrastat report.</span></span> <span data-ttu-id="70aec-115">Należy to zrobić poprzez utworzenie własnej pochodnej konfiguracji Intrastat na podstawie wystąpienia otrzymanego od Microsoft i w niej wprowadzić modyfikacje.</span><span class="sxs-lookup"><span data-stu-id="70aec-115">You need to do that by deriving our own instance of the Intrastat configuration from the Microsoft instance to make modifications.</span></span>  
5. <span data-ttu-id="70aec-116">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="70aec-116">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="70aec-117">W polu Nowy wprowadź wyrażenie „Pochodzi od nazwy: Intrastat (Niemcy), Microsoft”.</span><span class="sxs-lookup"><span data-stu-id="70aec-117">In the New field, enter 'Derive from Name: Intrastat (DE), Microsoft'.</span></span>
7. <span data-ttu-id="70aec-118">W polu Nazwa wpisz wyrażenie „Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="70aec-118">In the Name field, type 'Intrastat (DE) with counting & summing'.</span></span>
8. <span data-ttu-id="70aec-119">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="70aec-119">Click Create configuration.</span></span>

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a><span data-ttu-id="70aec-120">Konfigurowanie tego raportu w celu wykonania inwentaryzacji i sumowania na podstawie szczegółów danych wyjściowych</span><span class="sxs-lookup"><span data-stu-id="70aec-120">Configure this report to do counting and summation based on output details</span></span>
1. <span data-ttu-id="70aec-121">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="70aec-121">Click Designer.</span></span>
2. <span data-ttu-id="70aec-122">W polu Pobierz szczegóły rezultatu zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="70aec-122">Select Yes in the Collect output details field.</span></span>
    * <span data-ttu-id="70aec-123">Ta flaga będzie w czasie wykonywania uaktywniać proces gromadzenia szczegółów wyjściowych w celu wygenerowania pliku Intrastat.</span><span class="sxs-lookup"><span data-stu-id="70aec-123">This flag will activate at run-time the process of collecting output details for generating the Intrastat file.</span></span>  
    * <span data-ttu-id="70aec-124">Musisz wykonać inwentaryzację dla różnych kierunków Intrastat, dlatego dodasz dedykowane wyliczenie modelu do tej konfiguracji formatu używanej przez listę źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="70aec-124">You need to do counting for different Intrastat directions, so add a dedicated model enumeration to the data sources' list of this format configuration.</span></span>  
3. <span data-ttu-id="70aec-125">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="70aec-125">Click the Mapping tab.</span></span>
4. <span data-ttu-id="70aec-126">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="70aec-126">Click Add root to open the drop dialog.</span></span>
5. <span data-ttu-id="70aec-127">W drzewie zaznacz element „Model danych\Wyliczenie”.</span><span class="sxs-lookup"><span data-stu-id="70aec-127">In the tree, select 'Data model\Enumeration '.</span></span>
6. <span data-ttu-id="70aec-128">W polu Nazwa wpisz „Kierunek”.</span><span class="sxs-lookup"><span data-stu-id="70aec-128">In the Name field, type 'Direction'.</span></span>
7. <span data-ttu-id="70aec-129">W polu Wyliczenie modeli wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="70aec-129">In the Model enumeration field, enter or select a value.</span></span>
    * <span data-ttu-id="70aec-130">Wybierz wartość Kierunek.</span><span class="sxs-lookup"><span data-stu-id="70aec-130">Select the value Direction.</span></span>  
8. <span data-ttu-id="70aec-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="70aec-131">Click OK.</span></span>
9. <span data-ttu-id="70aec-132">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="70aec-132">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="70aec-133">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="70aec-133">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="70aec-134">W polu Nazwa wpisz „$BlockName”.</span><span class="sxs-lookup"><span data-stu-id="70aec-134">In the Name field, type '$BlockName'.</span></span>
12. <span data-ttu-id="70aec-135">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="70aec-135">Click Edit formula.</span></span>
13. <span data-ttu-id="70aec-136">W polu Formuła wpisz „blok”.</span><span class="sxs-lookup"><span data-stu-id="70aec-136">In the Formula field, enter '"block"'.</span></span>
14. <span data-ttu-id="70aec-137">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-137">Click Save.</span></span>
15. <span data-ttu-id="70aec-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-138">Close the page.</span></span>
16. <span data-ttu-id="70aec-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="70aec-139">Click OK.</span></span>
17. <span data-ttu-id="70aec-140">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="70aec-140">Click Add root to open the drop dialog.</span></span>
18. <span data-ttu-id="70aec-141">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="70aec-141">In the tree, select 'Functions\Calculated field'.</span></span>
19. <span data-ttu-id="70aec-142">W polu Nazwa wpisz „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="70aec-142">In the Name field, type '$RecName'.</span></span>
20. <span data-ttu-id="70aec-143">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="70aec-143">Click Edit formula.</span></span>
21. <span data-ttu-id="70aec-144">W polu Formuła wpisz „rekord”.</span><span class="sxs-lookup"><span data-stu-id="70aec-144">In the Formula field, enter '"record"'.</span></span>
22. <span data-ttu-id="70aec-145">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-145">Click Save.</span></span>
23. <span data-ttu-id="70aec-146">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-146">Close the page.</span></span>
24. <span data-ttu-id="70aec-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="70aec-147">Click OK.</span></span>
25. <span data-ttu-id="70aec-148">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="70aec-148">Click Add root to open the drop dialog.</span></span>
26. <span data-ttu-id="70aec-149">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="70aec-149">In the tree, select 'Functions\Calculated field'.</span></span>
27. <span data-ttu-id="70aec-150">W polu Nazwa wpisz „$InvName”.</span><span class="sxs-lookup"><span data-stu-id="70aec-150">In the Name field, type '$InvName'.</span></span>
28. <span data-ttu-id="70aec-151">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="70aec-151">Click Edit formula.</span></span>
29. <span data-ttu-id="70aec-152">W polu Formuła wpisz „InvoicedAmountEUR”.</span><span class="sxs-lookup"><span data-stu-id="70aec-152">In the Formula field, enter '"InvoicedAmountEUR"'.</span></span>
30. <span data-ttu-id="70aec-153">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-153">Click Save.</span></span>
31. <span data-ttu-id="70aec-154">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-154">Close the page.</span></span>
32. <span data-ttu-id="70aec-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="70aec-155">Click OK.</span></span>
33. <span data-ttu-id="70aec-156">W drzewie zaznacz element „Intrastat\Dane”.</span><span class="sxs-lookup"><span data-stu-id="70aec-156">In the tree, select 'Intrastat\Data'.</span></span>
34. <span data-ttu-id="70aec-157">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="70aec-157">Click Edit button for the 'Collected data key name' field</span></span>
35. <span data-ttu-id="70aec-158">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="70aec-158">Click Add data source.</span></span>
    * <span data-ttu-id="70aec-159">$BlockName</span><span class="sxs-lookup"><span data-stu-id="70aec-159">$BlockName</span></span>  
36. <span data-ttu-id="70aec-160">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-160">Click Save.</span></span>
37. <span data-ttu-id="70aec-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-161">Close the page.</span></span>
38. <span data-ttu-id="70aec-162">Kliknij przycisk Edytuj obok pola Wartość pobranego klucza danych.</span><span class="sxs-lookup"><span data-stu-id="70aec-162">Click the Edit button for the Collected data key value field.</span></span>
39. <span data-ttu-id="70aec-163">W polu Formuła wpisz wyrażenie „IF(Intrastat.CommodityRecord.Direction=Kierunek.Import, "Import", "Eksport")”.</span><span class="sxs-lookup"><span data-stu-id="70aec-163">In the Formula field, enter 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.</span></span>
    * <span data-ttu-id="70aec-164">IF(Intrastat.CommodityRecord.Direction=Kierunek.Import, "Import", "Eksport")</span><span class="sxs-lookup"><span data-stu-id="70aec-164">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span></span>  
40. <span data-ttu-id="70aec-165">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-165">Click Save.</span></span>
41. <span data-ttu-id="70aec-166">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-166">Close the page.</span></span>
    * <span data-ttu-id="70aec-167">Liczenie wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="70aec-167">Count the lines of this sequence.</span></span> <span data-ttu-id="70aec-168">Wyniki zostaną użyte z nazwą „blok” oddzielnie dla różnych kierunków.</span><span class="sxs-lookup"><span data-stu-id="70aec-168">The results will be used with the name "block" separately for different directions.</span></span> <span data-ttu-id="70aec-169">Wartość „Import” będzie używana dla wszelkich transakcji Intrastat przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="70aec-169">Value "Import" will be used for any arrivals Intrastat transactions.</span></span> <span data-ttu-id="70aec-170">Wartość „Eksport” będzie używana dla wszelkich transakcji Intrastat wysyłki.</span><span class="sxs-lookup"><span data-stu-id="70aec-170">The value "Export" will be used for any Intrastat dispatches transactions.</span></span> <span data-ttu-id="70aec-171">Potraktuj to jako wirtualny arkusz kalkulacyjny programu Excel.</span><span class="sxs-lookup"><span data-stu-id="70aec-171">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="70aec-172">Dla każdej transakcji będzie tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”.</span><span class="sxs-lookup"><span data-stu-id="70aec-172">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly.</span></span>  
42. <span data-ttu-id="70aec-173">W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja”.</span><span class="sxs-lookup"><span data-stu-id="70aec-173">In the tree, expand 'Intrastat\Data: Sequence'.</span></span>
43. <span data-ttu-id="70aec-174">W drzewie zaznacz element „Intrastat\Dane: Sekwencja\Przyjęcia?”.</span><span class="sxs-lookup"><span data-stu-id="70aec-174">In the tree, select 'Intrastat\Data: Sequence\Arrivals?'.</span></span>
44. <span data-ttu-id="70aec-175">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="70aec-175">Click Edit button for the 'Collected data key name' field.</span></span>
    * <span data-ttu-id="70aec-176">Liczenie wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="70aec-176">Count the lines of this sequence.</span></span> <span data-ttu-id="70aec-177">Wyniki zostaną zapamiętane pod nazwą „rekord”.</span><span class="sxs-lookup"><span data-stu-id="70aec-177">The results will be memorized using the name "record".</span></span>  
45. <span data-ttu-id="70aec-178">W drzewie zaznacz element „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="70aec-178">In the tree, select '$RecName'.</span></span>
46. <span data-ttu-id="70aec-179">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="70aec-179">Click Add data source.</span></span>
47. <span data-ttu-id="70aec-180">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-180">Click Save.</span></span>
48. <span data-ttu-id="70aec-181">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-181">Close the page.</span></span>
49. <span data-ttu-id="70aec-182">Kliknij przycisk Edytuj obok pola „Wartość pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="70aec-182">Click Edit button for the 'Collected data key value' field</span></span>
50. <span data-ttu-id="70aec-183">W polu Formuła wprowadź wyrażenie „Intrastat.CommodityRecord.CommodityCode”.</span><span class="sxs-lookup"><span data-stu-id="70aec-183">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
51. <span data-ttu-id="70aec-184">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-184">Click Save.</span></span>
52. <span data-ttu-id="70aec-185">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-185">Close the page.</span></span>
    * <span data-ttu-id="70aec-186">Liczenie wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="70aec-186">Count the lines of this sequence.</span></span> <span data-ttu-id="70aec-187">Wyniki zostaną użyte z nazwą „rekord” oddzielnie dla różnych kodów asortymentu.</span><span class="sxs-lookup"><span data-stu-id="70aec-187">The results will be used with the name "record" separately for different commodity codes.</span></span> <span data-ttu-id="70aec-188">Potraktuj to jako wirtualny arkusz kalkulacyjny programu Excel.</span><span class="sxs-lookup"><span data-stu-id="70aec-188">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="70aec-189">Dla każdej transakcji jest tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”, a drugi blok „rekord” jest wypełniany wartością kodu asortymentu.</span><span class="sxs-lookup"><span data-stu-id="70aec-189">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly and the second block "record" is filled with the commodity code value.</span></span>  
53. <span data-ttu-id="70aec-190">W drzewie zaznacz element „Intrastat\Dane: Sekwencja\Wysyłki?”.</span><span class="sxs-lookup"><span data-stu-id="70aec-190">In the tree, select 'Intrastat\Data: Sequence\Dispatches?'.</span></span>
54. <span data-ttu-id="70aec-191">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="70aec-191">Click Edit button for the 'Collected data key name' field</span></span>
55. <span data-ttu-id="70aec-192">W drzewie zaznacz element „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="70aec-192">In the tree, select '$RecName'.</span></span>
56. <span data-ttu-id="70aec-193">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="70aec-193">Click Add data source.</span></span>
57. <span data-ttu-id="70aec-194">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-194">Click Save.</span></span>
58. <span data-ttu-id="70aec-195">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-195">Close the page.</span></span>
59. <span data-ttu-id="70aec-196">Kliknij przycisk Edytuj obok pola „Wartość pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="70aec-196">Click the Edit button for the 'Collected data key value' field.</span></span>
60. <span data-ttu-id="70aec-197">W polu Formuła wprowadź wyrażenie „Intrastat.CommodityRecord.CommodityCode”.</span><span class="sxs-lookup"><span data-stu-id="70aec-197">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
61. <span data-ttu-id="70aec-198">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-198">Click Save.</span></span>
62. <span data-ttu-id="70aec-199">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-199">Close the page.</span></span>
63. <span data-ttu-id="70aec-200">W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja\Wysyłki: Sekwencja?”.</span><span class="sxs-lookup"><span data-stu-id="70aec-200">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?'.</span></span>
64. <span data-ttu-id="70aec-201">W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja\Wysyłki: Sekwencja?\Rekord = Intrastat.CommodityRecord”.</span><span class="sxs-lookup"><span data-stu-id="70aec-201">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?\Record =  Intrastat.CommodityRecord'.</span></span>
65. <span data-ttu-id="70aec-202">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="70aec-202">Click the Format tab.</span></span>
66. <span data-ttu-id="70aec-203">W drzewie zaznacz element „Intrastat\Dane\Wysyłki\Rekord\Kwota faktury w EUR”.</span><span class="sxs-lookup"><span data-stu-id="70aec-203">In the tree, select 'Intrastat\Data\Dispatches\Record\Invoice amount EUR'.</span></span>
67. <span data-ttu-id="70aec-204">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="70aec-204">Click the Mapping tab.</span></span>
68. <span data-ttu-id="70aec-205">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="70aec-205">Click the Edit button for the 'Collected data key name' field.</span></span>
69. <span data-ttu-id="70aec-206">W drzewie zaznacz element „$InvName”.</span><span class="sxs-lookup"><span data-stu-id="70aec-206">In the tree, select '$InvName'.</span></span>
70. <span data-ttu-id="70aec-207">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="70aec-207">Click Add data source.</span></span>
71. <span data-ttu-id="70aec-208">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-208">Click Save.</span></span>
72. <span data-ttu-id="70aec-209">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-209">Close the page.</span></span>
    * <span data-ttu-id="70aec-210">Podsumowanie wartości kwot zafakturowanych dla wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="70aec-210">Summarize the invoiced amount values for lines of this sequence.</span></span> <span data-ttu-id="70aec-211">Wyniki zostaną użyte z nazwą „InvoicedAmountEUR” oddzielnie dla różnych kierunków Intrastat kodów asortymentu.</span><span class="sxs-lookup"><span data-stu-id="70aec-211">The results will be used with the name "InvoicedAmountEUR" separately for different Intrastat directions and commodity codes.</span></span> <span data-ttu-id="70aec-212">Potraktuj to jak tworzenie wirtualnego arkusza kalkulacyjnego w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="70aec-212">Consider this to be a virtual creation in Excel spreadsheet.</span></span> <span data-ttu-id="70aec-213">Dla każdej transakcji będzie tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”.</span><span class="sxs-lookup"><span data-stu-id="70aec-213">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly.</span></span> <span data-ttu-id="70aec-214">Drugi blok „rekord” jest wypełniony wartością kodu asortymentu, a trzecia kolumna „InvoicedAmountEUR” jest wypełniona wartością kwoty faktury.</span><span class="sxs-lookup"><span data-stu-id="70aec-214">The second block "record" is filled with the commodity code value, and the third column "InvoicedAmountEUR" is filled with the invoice amount value.</span></span>  
73. <span data-ttu-id="70aec-215">W drzewie rozwiń węzeł „Intrastat\Dane\Przyjęcia?”.</span><span class="sxs-lookup"><span data-stu-id="70aec-215">In the tree, expand 'Intrastat\Data\Arrivals?'.</span></span>
74. <span data-ttu-id="70aec-216">W drzewie rozwiń węzeł „Intrastat\Dane\Przyjęcia?\Rekord = Intrastat.CommodityRecord”.</span><span class="sxs-lookup"><span data-stu-id="70aec-216">In the tree, expand 'Intrastat\Data\Arrivals?\Record =  Intrastat.CommodityRecord'.</span></span>
75. <span data-ttu-id="70aec-217">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="70aec-217">Click the Format tab.</span></span>
76. <span data-ttu-id="70aec-218">W drzewie zaznacz element „Intrastat\Dane\Przyjęcia\Rekord\Kwota faktury w EUR”.</span><span class="sxs-lookup"><span data-stu-id="70aec-218">In the tree, select 'Intrastat\Data\Arrivals\Record\Invoice amount EUR'.</span></span>
77. <span data-ttu-id="70aec-219">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="70aec-219">Click the Mapping tab.</span></span>
78. <span data-ttu-id="70aec-220">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="70aec-220">Click the Edit button for the 'Collected data key name' field.</span></span>
79. <span data-ttu-id="70aec-221">W drzewie zaznacz element „$InvName”.</span><span class="sxs-lookup"><span data-stu-id="70aec-221">In the tree, select '$InvName'.</span></span>
80. <span data-ttu-id="70aec-222">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="70aec-222">Click Add data source.</span></span>
81. <span data-ttu-id="70aec-223">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-223">Click Save.</span></span>
82. <span data-ttu-id="70aec-224">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-224">Close the page.</span></span>
83. <span data-ttu-id="70aec-225">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="70aec-225">Click Save.</span></span>
84. <span data-ttu-id="70aec-226">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="70aec-226">Close the page.</span></span>

