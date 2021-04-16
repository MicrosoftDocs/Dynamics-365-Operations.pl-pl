---
title: ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 2 — Konfigurowanie obliczeń)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego do zliczania i sumowania na podstawie danych już wygenerowanego tekstu wyjściowego. (część 2)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a14fe079515b176cbcda74852ae2ad456dd6434a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749028"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a><span data-ttu-id="85eef-104">ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 2 — Konfigurowanie obliczeń)</span><span class="sxs-lookup"><span data-stu-id="85eef-104">ER Configure format to do counting and summing (Part 2 - Configure computations)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="85eef-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="85eef-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="85eef-106">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="85eef-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="85eef-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 1: Tworzenie formatu)”.</span><span class="sxs-lookup"><span data-stu-id="85eef-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 1: Create format)" procedure.</span></span>

<span data-ttu-id="85eef-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="85eef-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a><span data-ttu-id="85eef-109">Tworzenie konfiguracji formatu w celu dodania szczegółów inwentaryzacji i sumowania</span><span class="sxs-lookup"><span data-stu-id="85eef-109">Create a format configuration to add counting and summing details</span></span>
1. <span data-ttu-id="85eef-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="85eef-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="85eef-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="85eef-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="85eef-112">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="85eef-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="85eef-113">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="85eef-113">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
    * <span data-ttu-id="85eef-114">Załóżmy, że trzeba dostosować format dostarczony przez firmę Microsoft, dodając wiersze zawierające szczegóły podsumowania na końcu raportu Intrastat.</span><span class="sxs-lookup"><span data-stu-id="85eef-114">Assume that you need to customize the format provided by Microsoft by adding lines with summary details at the end of the Intrastat report.</span></span> <span data-ttu-id="85eef-115">Należy to zrobić poprzez utworzenie własnej pochodnej konfiguracji Intrastat na podstawie wystąpienia otrzymanego od Microsoft i w niej wprowadzić modyfikacje.</span><span class="sxs-lookup"><span data-stu-id="85eef-115">You need to do that by deriving our own instance of the Intrastat configuration from the Microsoft instance to make modifications.</span></span>  
5. <span data-ttu-id="85eef-116">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85eef-116">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="85eef-117">W polu Nowy wprowadź wyrażenie „Pochodzi od nazwy: Intrastat (Niemcy), Microsoft”.</span><span class="sxs-lookup"><span data-stu-id="85eef-117">In the New field, enter 'Derive from Name: Intrastat (DE), Microsoft'.</span></span>
7. <span data-ttu-id="85eef-118">W polu Nazwa wpisz wyrażenie „Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="85eef-118">In the Name field, type 'Intrastat (DE) with counting & summing'.</span></span>
8. <span data-ttu-id="85eef-119">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="85eef-119">Click Create configuration.</span></span>

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a><span data-ttu-id="85eef-120">Konfigurowanie tego raportu w celu wykonania inwentaryzacji i sumowania na podstawie szczegółów danych wyjściowych</span><span class="sxs-lookup"><span data-stu-id="85eef-120">Configure this report to do counting and summation based on output details</span></span>
1. <span data-ttu-id="85eef-121">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="85eef-121">Click Designer.</span></span>
2. <span data-ttu-id="85eef-122">W polu Pobierz szczegóły rezultatu zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="85eef-122">Select Yes in the Collect output details field.</span></span>
    * <span data-ttu-id="85eef-123">Ta flaga będzie w czasie wykonywania uaktywniać proces gromadzenia szczegółów wyjściowych w celu wygenerowania pliku Intrastat.</span><span class="sxs-lookup"><span data-stu-id="85eef-123">This flag will activate at run-time the process of collecting output details for generating the Intrastat file.</span></span>  
    * <span data-ttu-id="85eef-124">Musisz wykonać inwentaryzację dla różnych kierunków Intrastat, dlatego dodasz dedykowane wyliczenie modelu do tej konfiguracji formatu używanej przez listę źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="85eef-124">You need to do counting for different Intrastat directions, so add a dedicated model enumeration to the data sources' list of this format configuration.</span></span>  
3. <span data-ttu-id="85eef-125">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="85eef-125">Click the Mapping tab.</span></span>
4. <span data-ttu-id="85eef-126">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85eef-126">Click Add root to open the drop dialog.</span></span>
5. <span data-ttu-id="85eef-127">W drzewie zaznacz element „Model danych\Wyliczenie”.</span><span class="sxs-lookup"><span data-stu-id="85eef-127">In the tree, select 'Data model\Enumeration '.</span></span>
6. <span data-ttu-id="85eef-128">W polu Nazwa wpisz „Kierunek”.</span><span class="sxs-lookup"><span data-stu-id="85eef-128">In the Name field, type 'Direction'.</span></span>
7. <span data-ttu-id="85eef-129">W polu Wyliczenie modeli wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="85eef-129">In the Model enumeration field, enter or select a value.</span></span>
    * <span data-ttu-id="85eef-130">Wybierz wartość Kierunek.</span><span class="sxs-lookup"><span data-stu-id="85eef-130">Select the value Direction.</span></span>  
8. <span data-ttu-id="85eef-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="85eef-131">Click OK.</span></span>
9. <span data-ttu-id="85eef-132">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85eef-132">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="85eef-133">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="85eef-133">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="85eef-134">W polu Nazwa wpisz „$BlockName”.</span><span class="sxs-lookup"><span data-stu-id="85eef-134">In the Name field, type '$BlockName'.</span></span>
12. <span data-ttu-id="85eef-135">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="85eef-135">Click Edit formula.</span></span>
13. <span data-ttu-id="85eef-136">W polu Formuła wpisz „blok”.</span><span class="sxs-lookup"><span data-stu-id="85eef-136">In the Formula field, enter '"block"'.</span></span>
14. <span data-ttu-id="85eef-137">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-137">Click Save.</span></span>
15. <span data-ttu-id="85eef-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-138">Close the page.</span></span>
16. <span data-ttu-id="85eef-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="85eef-139">Click OK.</span></span>
17. <span data-ttu-id="85eef-140">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85eef-140">Click Add root to open the drop dialog.</span></span>
18. <span data-ttu-id="85eef-141">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="85eef-141">In the tree, select 'Functions\Calculated field'.</span></span>
19. <span data-ttu-id="85eef-142">W polu Nazwa wpisz „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="85eef-142">In the Name field, type '$RecName'.</span></span>
20. <span data-ttu-id="85eef-143">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="85eef-143">Click Edit formula.</span></span>
21. <span data-ttu-id="85eef-144">W polu Formuła wpisz „rekord”.</span><span class="sxs-lookup"><span data-stu-id="85eef-144">In the Formula field, enter '"record"'.</span></span>
22. <span data-ttu-id="85eef-145">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-145">Click Save.</span></span>
23. <span data-ttu-id="85eef-146">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-146">Close the page.</span></span>
24. <span data-ttu-id="85eef-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="85eef-147">Click OK.</span></span>
25. <span data-ttu-id="85eef-148">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85eef-148">Click Add root to open the drop dialog.</span></span>
26. <span data-ttu-id="85eef-149">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="85eef-149">In the tree, select 'Functions\Calculated field'.</span></span>
27. <span data-ttu-id="85eef-150">W polu Nazwa wpisz „$InvName”.</span><span class="sxs-lookup"><span data-stu-id="85eef-150">In the Name field, type '$InvName'.</span></span>
28. <span data-ttu-id="85eef-151">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="85eef-151">Click Edit formula.</span></span>
29. <span data-ttu-id="85eef-152">W polu Formuła wpisz „InvoicedAmountEUR”.</span><span class="sxs-lookup"><span data-stu-id="85eef-152">In the Formula field, enter '"InvoicedAmountEUR"'.</span></span>
30. <span data-ttu-id="85eef-153">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-153">Click Save.</span></span>
31. <span data-ttu-id="85eef-154">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-154">Close the page.</span></span>
32. <span data-ttu-id="85eef-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="85eef-155">Click OK.</span></span>
33. <span data-ttu-id="85eef-156">W drzewie zaznacz element „Intrastat\Dane”.</span><span class="sxs-lookup"><span data-stu-id="85eef-156">In the tree, select 'Intrastat\Data'.</span></span>
34. <span data-ttu-id="85eef-157">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="85eef-157">Click Edit button for the 'Collected data key name' field</span></span>
35. <span data-ttu-id="85eef-158">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="85eef-158">Click Add data source.</span></span>
    * <span data-ttu-id="85eef-159">$BlockName</span><span class="sxs-lookup"><span data-stu-id="85eef-159">$BlockName</span></span>  
36. <span data-ttu-id="85eef-160">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-160">Click Save.</span></span>
37. <span data-ttu-id="85eef-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-161">Close the page.</span></span>
38. <span data-ttu-id="85eef-162">Kliknij przycisk Edytuj obok pola Wartość pobranego klucza danych.</span><span class="sxs-lookup"><span data-stu-id="85eef-162">Click the Edit button for the Collected data key value field.</span></span>
39. <span data-ttu-id="85eef-163">W polu Formuła wpisz wyrażenie „IF(Intrastat.CommodityRecord.Direction=Kierunek.Import, "Import", "Eksport")”.</span><span class="sxs-lookup"><span data-stu-id="85eef-163">In the Formula field, enter 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.</span></span>
    * <span data-ttu-id="85eef-164">IF(Intrastat.CommodityRecord.Direction=Kierunek.Import, "Import", "Eksport")</span><span class="sxs-lookup"><span data-stu-id="85eef-164">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span></span>  
40. <span data-ttu-id="85eef-165">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-165">Click Save.</span></span>
41. <span data-ttu-id="85eef-166">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-166">Close the page.</span></span>
    * <span data-ttu-id="85eef-167">Liczenie wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="85eef-167">Count the lines of this sequence.</span></span> <span data-ttu-id="85eef-168">Wyniki zostaną użyte z nazwą „blok” oddzielnie dla różnych kierunków.</span><span class="sxs-lookup"><span data-stu-id="85eef-168">The results will be used with the name "block" separately for different directions.</span></span> <span data-ttu-id="85eef-169">Wartość „Import” będzie używana dla wszelkich transakcji Intrastat przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="85eef-169">Value "Import" will be used for any arrivals Intrastat transactions.</span></span> <span data-ttu-id="85eef-170">Wartość „Eksport” będzie używana dla wszelkich transakcji Intrastat wysyłki.</span><span class="sxs-lookup"><span data-stu-id="85eef-170">The value "Export" will be used for any Intrastat dispatches transactions.</span></span> <span data-ttu-id="85eef-171">Potraktuj to jako wirtualny arkusz kalkulacyjny programu Excel.</span><span class="sxs-lookup"><span data-stu-id="85eef-171">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="85eef-172">Dla każdej transakcji będzie tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”.</span><span class="sxs-lookup"><span data-stu-id="85eef-172">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly.</span></span>  
42. <span data-ttu-id="85eef-173">W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja”.</span><span class="sxs-lookup"><span data-stu-id="85eef-173">In the tree, expand 'Intrastat\Data: Sequence'.</span></span>
43. <span data-ttu-id="85eef-174">W drzewie zaznacz element „Intrastat\Dane: Sekwencja\Przyjęcia?”.</span><span class="sxs-lookup"><span data-stu-id="85eef-174">In the tree, select 'Intrastat\Data: Sequence\Arrivals?'.</span></span>
44. <span data-ttu-id="85eef-175">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="85eef-175">Click Edit button for the 'Collected data key name' field.</span></span>
    * <span data-ttu-id="85eef-176">Liczenie wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="85eef-176">Count the lines of this sequence.</span></span> <span data-ttu-id="85eef-177">Wyniki zostaną zapamiętane pod nazwą „rekord”.</span><span class="sxs-lookup"><span data-stu-id="85eef-177">The results will be memorized using the name "record".</span></span>  
45. <span data-ttu-id="85eef-178">W drzewie zaznacz element „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="85eef-178">In the tree, select '$RecName'.</span></span>
46. <span data-ttu-id="85eef-179">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="85eef-179">Click Add data source.</span></span>
47. <span data-ttu-id="85eef-180">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-180">Click Save.</span></span>
48. <span data-ttu-id="85eef-181">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-181">Close the page.</span></span>
49. <span data-ttu-id="85eef-182">Kliknij przycisk Edytuj obok pola „Wartość pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="85eef-182">Click Edit button for the 'Collected data key value' field</span></span>
50. <span data-ttu-id="85eef-183">W polu Formuła wprowadź wyrażenie „Intrastat.CommodityRecord.CommodityCode”.</span><span class="sxs-lookup"><span data-stu-id="85eef-183">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
51. <span data-ttu-id="85eef-184">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-184">Click Save.</span></span>
52. <span data-ttu-id="85eef-185">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-185">Close the page.</span></span>
    * <span data-ttu-id="85eef-186">Liczenie wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="85eef-186">Count the lines of this sequence.</span></span> <span data-ttu-id="85eef-187">Wyniki zostaną użyte z nazwą „rekord” oddzielnie dla różnych kodów asortymentu.</span><span class="sxs-lookup"><span data-stu-id="85eef-187">The results will be used with the name "record" separately for different commodity codes.</span></span> <span data-ttu-id="85eef-188">Potraktuj to jako wirtualny arkusz kalkulacyjny programu Excel.</span><span class="sxs-lookup"><span data-stu-id="85eef-188">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="85eef-189">Dla każdej transakcji jest tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”, a drugi blok „rekord” jest wypełniany wartością kodu asortymentu.</span><span class="sxs-lookup"><span data-stu-id="85eef-189">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly and the second block "record" is filled with the commodity code value.</span></span>  
53. <span data-ttu-id="85eef-190">W drzewie zaznacz element „Intrastat\Dane: Sekwencja\Wysyłki?”.</span><span class="sxs-lookup"><span data-stu-id="85eef-190">In the tree, select 'Intrastat\Data: Sequence\Dispatches?'.</span></span>
54. <span data-ttu-id="85eef-191">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="85eef-191">Click Edit button for the 'Collected data key name' field</span></span>
55. <span data-ttu-id="85eef-192">W drzewie zaznacz element „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="85eef-192">In the tree, select '$RecName'.</span></span>
56. <span data-ttu-id="85eef-193">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="85eef-193">Click Add data source.</span></span>
57. <span data-ttu-id="85eef-194">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-194">Click Save.</span></span>
58. <span data-ttu-id="85eef-195">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-195">Close the page.</span></span>
59. <span data-ttu-id="85eef-196">Kliknij przycisk Edytuj obok pola „Wartość pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="85eef-196">Click the Edit button for the 'Collected data key value' field.</span></span>
60. <span data-ttu-id="85eef-197">W polu Formuła wprowadź wyrażenie „Intrastat.CommodityRecord.CommodityCode”.</span><span class="sxs-lookup"><span data-stu-id="85eef-197">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
61. <span data-ttu-id="85eef-198">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-198">Click Save.</span></span>
62. <span data-ttu-id="85eef-199">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-199">Close the page.</span></span>
63. <span data-ttu-id="85eef-200">W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja\Wysyłki: Sekwencja?”.</span><span class="sxs-lookup"><span data-stu-id="85eef-200">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?'.</span></span>
64. <span data-ttu-id="85eef-201">W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja\Wysyłki: Sekwencja?\Rekord = Intrastat.CommodityRecord”.</span><span class="sxs-lookup"><span data-stu-id="85eef-201">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?\Record =  Intrastat.CommodityRecord'.</span></span>
65. <span data-ttu-id="85eef-202">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="85eef-202">Click the Format tab.</span></span>
66. <span data-ttu-id="85eef-203">W drzewie zaznacz element „Intrastat\Dane\Wysyłki\Rekord\Kwota faktury w EUR”.</span><span class="sxs-lookup"><span data-stu-id="85eef-203">In the tree, select 'Intrastat\Data\Dispatches\Record\Invoice amount EUR'.</span></span>
67. <span data-ttu-id="85eef-204">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="85eef-204">Click the Mapping tab.</span></span>
68. <span data-ttu-id="85eef-205">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="85eef-205">Click the Edit button for the 'Collected data key name' field.</span></span>
69. <span data-ttu-id="85eef-206">W drzewie zaznacz element „$InvName”.</span><span class="sxs-lookup"><span data-stu-id="85eef-206">In the tree, select '$InvName'.</span></span>
70. <span data-ttu-id="85eef-207">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="85eef-207">Click Add data source.</span></span>
71. <span data-ttu-id="85eef-208">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-208">Click Save.</span></span>
72. <span data-ttu-id="85eef-209">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-209">Close the page.</span></span>
    * <span data-ttu-id="85eef-210">Podsumowanie wartości kwot zafakturowanych dla wierszy tej kolejnej sesji.</span><span class="sxs-lookup"><span data-stu-id="85eef-210">Summarize the invoiced amount values for lines of this sequence.</span></span> <span data-ttu-id="85eef-211">Wyniki zostaną użyte z nazwą „InvoicedAmountEUR” oddzielnie dla różnych kierunków Intrastat kodów asortymentu.</span><span class="sxs-lookup"><span data-stu-id="85eef-211">The results will be used with the name "InvoicedAmountEUR" separately for different Intrastat directions and commodity codes.</span></span> <span data-ttu-id="85eef-212">Potraktuj to jak tworzenie wirtualnego arkusza kalkulacyjnego w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="85eef-212">Consider this to be a virtual creation in Excel spreadsheet.</span></span> <span data-ttu-id="85eef-213">Dla każdej transakcji będzie tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”.</span><span class="sxs-lookup"><span data-stu-id="85eef-213">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly.</span></span> <span data-ttu-id="85eef-214">Drugi blok „rekord” jest wypełniony wartością kodu asortymentu, a trzecia kolumna „InvoicedAmountEUR” jest wypełniona wartością kwoty faktury.</span><span class="sxs-lookup"><span data-stu-id="85eef-214">The second block "record" is filled with the commodity code value, and the third column "InvoicedAmountEUR" is filled with the invoice amount value.</span></span>  
73. <span data-ttu-id="85eef-215">W drzewie rozwiń węzeł „Intrastat\Dane\Przyjęcia?”.</span><span class="sxs-lookup"><span data-stu-id="85eef-215">In the tree, expand 'Intrastat\Data\Arrivals?'.</span></span>
74. <span data-ttu-id="85eef-216">W drzewie rozwiń węzeł „Intrastat\Dane\Przyjęcia?\Rekord = Intrastat.CommodityRecord”.</span><span class="sxs-lookup"><span data-stu-id="85eef-216">In the tree, expand 'Intrastat\Data\Arrivals?\Record =  Intrastat.CommodityRecord'.</span></span>
75. <span data-ttu-id="85eef-217">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="85eef-217">Click the Format tab.</span></span>
76. <span data-ttu-id="85eef-218">W drzewie zaznacz element „Intrastat\Dane\Przyjęcia\Rekord\Kwota faktury w EUR”.</span><span class="sxs-lookup"><span data-stu-id="85eef-218">In the tree, select 'Intrastat\Data\Arrivals\Record\Invoice amount EUR'.</span></span>
77. <span data-ttu-id="85eef-219">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="85eef-219">Click the Mapping tab.</span></span>
78. <span data-ttu-id="85eef-220">Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.</span><span class="sxs-lookup"><span data-stu-id="85eef-220">Click the Edit button for the 'Collected data key name' field.</span></span>
79. <span data-ttu-id="85eef-221">W drzewie zaznacz element „$InvName”.</span><span class="sxs-lookup"><span data-stu-id="85eef-221">In the tree, select '$InvName'.</span></span>
80. <span data-ttu-id="85eef-222">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="85eef-222">Click Add data source.</span></span>
81. <span data-ttu-id="85eef-223">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-223">Click Save.</span></span>
82. <span data-ttu-id="85eef-224">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-224">Close the page.</span></span>
83. <span data-ttu-id="85eef-225">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85eef-225">Click Save.</span></span>
84. <span data-ttu-id="85eef-226">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85eef-226">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]