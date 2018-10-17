--- 
title: "ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 3 — Używanie obliczeń do wygenerowania danych wyjściowych)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 5c870c134a9dae81cd619268bed7ce545bdd5f52
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="er-configure-format-to-do-counting-and-summing-part-3-use-computations-to-make-the-output"></a><span data-ttu-id="450fd-103">ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 3: Używanie obliczeń do wygenerowania danych wyjściowych)</span><span class="sxs-lookup"><span data-stu-id="450fd-103">ER Configure format to do counting and summing (Part 3: Use computations to make the output)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="450fd-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="450fd-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="450fd-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="450fd-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="450fd-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 2: Konfigurowanie obliczeń)”.</span><span class="sxs-lookup"><span data-stu-id="450fd-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 2: Configure computations)” procedure.</span></span>

<span data-ttu-id="450fd-107">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="450fd-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="450fd-108">Konfigurowanie tego raportu w celu używania informacji o inwentaryzacji i sumowaniu</span><span class="sxs-lookup"><span data-stu-id="450fd-108">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="450fd-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="450fd-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="450fd-110">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="450fd-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="450fd-111">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="450fd-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="450fd-112">W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="450fd-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="450fd-113">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="450fd-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="450fd-114">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="450fd-114">Click Designer.</span></span>
7. <span data-ttu-id="450fd-115">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="450fd-115">Click the Mapping tab.</span></span>
8. <span data-ttu-id="450fd-116">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="450fd-116">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="450fd-117">Dodaj nowe źródło danych w celu uzyskania listy zapamiętanych bloków.</span><span class="sxs-lookup"><span data-stu-id="450fd-117">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="450fd-118">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="450fd-118">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="450fd-119">W polu Nazwa wpisz „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="450fd-119">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="450fd-120">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="450fd-120">$BlocksList</span></span>  
11. <span data-ttu-id="450fd-121">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="450fd-121">Click Edit formula.</span></span>
12. <span data-ttu-id="450fd-122">W drzewie zaznacz element „Funkcje gromadzenia danych\COLLECTEDLIST”.</span><span class="sxs-lookup"><span data-stu-id="450fd-122">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="450fd-123">Kliknij opcję Dodaj funkcję.</span><span class="sxs-lookup"><span data-stu-id="450fd-123">Click Add function.</span></span>
14. <span data-ttu-id="450fd-124">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="450fd-124">Click Add data source.</span></span>
15. <span data-ttu-id="450fd-125">W polu Formuła wpisz „COLLECTEDLIST('$BlockName', ”.</span><span class="sxs-lookup"><span data-stu-id="450fd-125">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="450fd-126">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="450fd-126">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="450fd-127">W polu Formuła wpisz „COLLECTEDLIST('$BlockName', "\*")”.</span><span class="sxs-lookup"><span data-stu-id="450fd-127">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="450fd-128">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="450fd-128">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="450fd-129">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="450fd-129">Click Save.</span></span>
    * <span data-ttu-id="450fd-130">Wzorzec "\*" oznacza, że wszystkie bloki zostaną włączone do listy dla tego rekordu.</span><span class="sxs-lookup"><span data-stu-id="450fd-130">The pattern “\*” means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="450fd-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="450fd-131">Close the page.</span></span>
19. <span data-ttu-id="450fd-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="450fd-132">Click OK.</span></span>
20. <span data-ttu-id="450fd-133">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="450fd-133">Click the Format tab.</span></span>
21. <span data-ttu-id="450fd-134">W drzewie zaznacz element „Intrastat\Dane”.</span><span class="sxs-lookup"><span data-stu-id="450fd-134">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="450fd-135">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="450fd-135">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="450fd-136">W drzewie zaznacz element „Tekst\Sekwencja”.</span><span class="sxs-lookup"><span data-stu-id="450fd-136">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="450fd-137">W polu Nazwa wpisz „Sumy według bloków”.</span><span class="sxs-lookup"><span data-stu-id="450fd-137">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="450fd-138">Sumy według bloków</span><span class="sxs-lookup"><span data-stu-id="450fd-138">Totals by blocks</span></span>  
25. <span data-ttu-id="450fd-139">W polu Znaki specjalne wybierz opcję „Nowy wiersz — Windows (CR LF)”.</span><span class="sxs-lookup"><span data-stu-id="450fd-139">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="450fd-140">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="450fd-140">Click OK.</span></span>
27. <span data-ttu-id="450fd-141">W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków”.</span><span class="sxs-lookup"><span data-stu-id="450fd-141">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="450fd-142">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="450fd-142">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="450fd-143">W drzewie zaznacz element „Tekst\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="450fd-143">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="450fd-144">W polu Nazwa wpisz „Kod bloku”.</span><span class="sxs-lookup"><span data-stu-id="450fd-144">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="450fd-145">Kod bloku</span><span class="sxs-lookup"><span data-stu-id="450fd-145">Block code</span></span>  
31. <span data-ttu-id="450fd-146">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="450fd-146">Click OK.</span></span>
32. <span data-ttu-id="450fd-147">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="450fd-147">Click Add String.</span></span>
33. <span data-ttu-id="450fd-148">W polu Nazwa wpisz „Inwentaryzacja wierszy”.</span><span class="sxs-lookup"><span data-stu-id="450fd-148">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="450fd-149">Inwentaryzacja wierszy</span><span class="sxs-lookup"><span data-stu-id="450fd-149">Lines counting</span></span>  
34. <span data-ttu-id="450fd-150">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="450fd-150">Click OK.</span></span>
35. <span data-ttu-id="450fd-151">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="450fd-151">Click Add String.</span></span>
36. <span data-ttu-id="450fd-152">W polu Nazwa wpisz „Łączna kwota”.</span><span class="sxs-lookup"><span data-stu-id="450fd-152">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="450fd-153">Łączna liczba</span><span class="sxs-lookup"><span data-stu-id="450fd-153">Total amount</span></span>  
37. <span data-ttu-id="450fd-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="450fd-154">Click OK.</span></span>
38. <span data-ttu-id="450fd-155">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="450fd-155">Click the Mapping tab.</span></span>
39. <span data-ttu-id="450fd-156">W drzewie wybierz węzeł „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="450fd-156">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="450fd-157">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="450fd-157">Click Bind.</span></span>
    * <span data-ttu-id="450fd-158">Utwórz wiersz podsumowania dla każdego zapamiętanego bloku.</span><span class="sxs-lookup"><span data-stu-id="450fd-158">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="450fd-159">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="450fd-159">Click the Format tab.</span></span>
42. <span data-ttu-id="450fd-160">W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków\Kod bloku”.</span><span class="sxs-lookup"><span data-stu-id="450fd-160">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="450fd-161">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="450fd-161">Click the Mapping tab.</span></span>
44. <span data-ttu-id="450fd-162">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="450fd-162">Click Edit formula.</span></span>
45. <span data-ttu-id="450fd-163">W polu Formuła wpisz „"Identyfikator bloku: " & ”.</span><span class="sxs-lookup"><span data-stu-id="450fd-163">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="450fd-164">"Identyfikator bloku: " &</span><span class="sxs-lookup"><span data-stu-id="450fd-164">"Block id: " &</span></span>  
46. <span data-ttu-id="450fd-165">W drzewie rozwiń węzeł „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="450fd-165">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="450fd-166">W drzewie zaznacz element „$BlocksList\Wartość”.</span><span class="sxs-lookup"><span data-stu-id="450fd-166">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="450fd-167">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="450fd-167">Click Add data source.</span></span>
49. <span data-ttu-id="450fd-168">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="450fd-168">Click Save.</span></span>
50. <span data-ttu-id="450fd-169">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="450fd-169">Close the page.</span></span>
51. <span data-ttu-id="450fd-170">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="450fd-170">Click the Format tab.</span></span>
52. <span data-ttu-id="450fd-171">W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków\Inwentaryzacja wierszy”.</span><span class="sxs-lookup"><span data-stu-id="450fd-171">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="450fd-172">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="450fd-172">Click the Mapping tab.</span></span>
54. <span data-ttu-id="450fd-173">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="450fd-173">Click Edit formula.</span></span>
    * <span data-ttu-id="450fd-174">Utwórz dane wyjściowe dla liczby wierszy każdego bloku przedstawionej w tym raporcie.</span><span class="sxs-lookup"><span data-stu-id="450fd-174">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="450fd-175">W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & ”.</span><span class="sxs-lookup"><span data-stu-id="450fd-175">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="450fd-176">"Liczba wierszy w tym bloku: " &</span><span class="sxs-lookup"><span data-stu-id="450fd-176">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="450fd-177">W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(”.</span><span class="sxs-lookup"><span data-stu-id="450fd-177">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="450fd-178">"Liczba wierszy w tym bloku: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="450fd-178">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="450fd-179">W drzewie zaznacz element „Funkcje gromadzenia danych\COUNTIFS”.</span><span class="sxs-lookup"><span data-stu-id="450fd-179">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="450fd-180">Kliknij opcję Dodaj funkcję.</span><span class="sxs-lookup"><span data-stu-id="450fd-180">Click Add function.</span></span>
59. <span data-ttu-id="450fd-181">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="450fd-181">Click Add data source.</span></span>
60. <span data-ttu-id="450fd-182">W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', ”.</span><span class="sxs-lookup"><span data-stu-id="450fd-182">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="450fd-183">"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="450fd-183">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="450fd-184">W drzewie rozwiń węzeł „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="450fd-184">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="450fd-185">W drzewie zaznacz element „$BlocksList\Wartość”.</span><span class="sxs-lookup"><span data-stu-id="450fd-185">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="450fd-186">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="450fd-186">Click Add data source.</span></span>
64. <span data-ttu-id="450fd-187">W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość, ”.</span><span class="sxs-lookup"><span data-stu-id="450fd-187">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="450fd-188">"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość,</span><span class="sxs-lookup"><span data-stu-id="450fd-188">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="450fd-189">W drzewie zaznacz element „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="450fd-189">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="450fd-190">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="450fd-190">Click Add data source.</span></span>
67. <span data-ttu-id="450fd-191">W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość, '$RecName', "\*"))”.</span><span class="sxs-lookup"><span data-stu-id="450fd-191">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="450fd-192">"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="450fd-192">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="450fd-193">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="450fd-193">Click Save.</span></span>
69. <span data-ttu-id="450fd-194">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="450fd-194">Close the page.</span></span>
70. <span data-ttu-id="450fd-195">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="450fd-195">Click the Format tab.</span></span>
71. <span data-ttu-id="450fd-196">W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków\Łączna kwota”.</span><span class="sxs-lookup"><span data-stu-id="450fd-196">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="450fd-197">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="450fd-197">Click the Mapping tab.</span></span>
73. <span data-ttu-id="450fd-198">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="450fd-198">Click Edit formula.</span></span>
    * <span data-ttu-id="450fd-199">Utwórz dane wyjściowe, który będą sumą kwot zafakturowanych dla wszystkich bloków przedstawionych w tym raporcie.</span><span class="sxs-lookup"><span data-stu-id="450fd-199">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="450fd-200">W polu Formuła wpisz „"Suma zafakturowanych kwot: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Wartość, '$RecName', "\*"))”.</span><span class="sxs-lookup"><span data-stu-id="450fd-200">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="450fd-201">"Suma zafakturowanych kwot: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Wartość, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="450fd-201">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="450fd-202">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="450fd-202">Click Save.</span></span>
76. <span data-ttu-id="450fd-203">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="450fd-203">Close the page.</span></span>
77. <span data-ttu-id="450fd-204">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="450fd-204">Click Save.</span></span>
78. <span data-ttu-id="450fd-205">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="450fd-205">Close the page.</span></span>


