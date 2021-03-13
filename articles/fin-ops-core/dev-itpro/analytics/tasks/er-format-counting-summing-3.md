---
title: ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 3 — Używanie obliczeń do wygenerowania danych wyjściowych)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego do zliczania i sumowania na podstawie danych już wygenerowanego tekstu wyjściowego. (część 3)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a69dd28051d8e98643eb95c663525075bed8dec
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092979"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="96dcf-104">ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 3 — Używanie obliczeń do wygenerowania danych wyjściowych)</span><span class="sxs-lookup"><span data-stu-id="96dcf-104">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="96dcf-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="96dcf-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="96dcf-106">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="96dcf-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="96dcf-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 2: Konfigurowanie obliczeń)”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="96dcf-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="96dcf-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="96dcf-109">Konfigurowanie tego raportu w celu używania informacji o inwentaryzacji i sumowaniu</span><span class="sxs-lookup"><span data-stu-id="96dcf-109">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="96dcf-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="96dcf-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="96dcf-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="96dcf-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="96dcf-112">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="96dcf-113">W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="96dcf-114">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="96dcf-115">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="96dcf-115">Click Designer.</span></span>
7. <span data-ttu-id="96dcf-116">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="96dcf-116">Click the Mapping tab.</span></span>
8. <span data-ttu-id="96dcf-117">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="96dcf-117">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="96dcf-118">Dodaj nowe źródło danych w celu uzyskania listy zapamiętanych bloków.</span><span class="sxs-lookup"><span data-stu-id="96dcf-118">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="96dcf-119">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-119">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="96dcf-120">W polu Nazwa wpisz „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-120">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="96dcf-121">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="96dcf-121">$BlocksList</span></span>  
11. <span data-ttu-id="96dcf-122">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="96dcf-122">Click Edit formula.</span></span>
12. <span data-ttu-id="96dcf-123">W drzewie zaznacz element „Funkcje gromadzenia danych\COLLECTEDLIST”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-123">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="96dcf-124">Kliknij opcję Dodaj funkcję.</span><span class="sxs-lookup"><span data-stu-id="96dcf-124">Click Add function.</span></span>
14. <span data-ttu-id="96dcf-125">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="96dcf-125">Click Add data source.</span></span>
15. <span data-ttu-id="96dcf-126">W polu Formuła wpisz „COLLECTEDLIST('$BlockName', ”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-126">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="96dcf-127">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="96dcf-127">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="96dcf-128">W polu Formuła wpisz „COLLECTEDLIST('$BlockName', "\*")”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-128">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="96dcf-129">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="96dcf-129">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="96dcf-130">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="96dcf-130">Click Save.</span></span>
    * <span data-ttu-id="96dcf-131">Wzorzec "\*" oznacza, że wszystkie bloki zostaną włączone do listy dla tego rekordu.</span><span class="sxs-lookup"><span data-stu-id="96dcf-131">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="96dcf-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="96dcf-132">Close the page.</span></span>
19. <span data-ttu-id="96dcf-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="96dcf-133">Click OK.</span></span>
20. <span data-ttu-id="96dcf-134">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="96dcf-134">Click the Format tab.</span></span>
21. <span data-ttu-id="96dcf-135">W drzewie zaznacz element „Intrastat\Dane”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-135">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="96dcf-136">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="96dcf-136">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="96dcf-137">W drzewie zaznacz element „Tekst\Sekwencja”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-137">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="96dcf-138">W polu Nazwa wpisz „Sumy według bloków”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-138">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="96dcf-139">Sumy według bloków</span><span class="sxs-lookup"><span data-stu-id="96dcf-139">Totals by blocks</span></span>  
25. <span data-ttu-id="96dcf-140">W polu Znaki specjalne wybierz opcję „Nowy wiersz — Windows (CR LF)”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-140">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="96dcf-141">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="96dcf-141">Click OK.</span></span>
27. <span data-ttu-id="96dcf-142">W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-142">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="96dcf-143">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="96dcf-143">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="96dcf-144">W drzewie zaznacz element „Tekst\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-144">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="96dcf-145">W polu Nazwa wpisz „Kod bloku”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-145">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="96dcf-146">Kod bloku</span><span class="sxs-lookup"><span data-stu-id="96dcf-146">Block code</span></span>  
31. <span data-ttu-id="96dcf-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="96dcf-147">Click OK.</span></span>
32. <span data-ttu-id="96dcf-148">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="96dcf-148">Click Add String.</span></span>
33. <span data-ttu-id="96dcf-149">W polu Nazwa wpisz „Inwentaryzacja wierszy”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-149">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="96dcf-150">Inwentaryzacja wierszy</span><span class="sxs-lookup"><span data-stu-id="96dcf-150">Lines counting</span></span>  
34. <span data-ttu-id="96dcf-151">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="96dcf-151">Click OK.</span></span>
35. <span data-ttu-id="96dcf-152">Kliknij opcję Dodaj ciąg.</span><span class="sxs-lookup"><span data-stu-id="96dcf-152">Click Add String.</span></span>
36. <span data-ttu-id="96dcf-153">W polu Nazwa wpisz „Łączna kwota”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-153">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="96dcf-154">Łączna liczba</span><span class="sxs-lookup"><span data-stu-id="96dcf-154">Total amount</span></span>  
37. <span data-ttu-id="96dcf-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="96dcf-155">Click OK.</span></span>
38. <span data-ttu-id="96dcf-156">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="96dcf-156">Click the Mapping tab.</span></span>
39. <span data-ttu-id="96dcf-157">W drzewie wybierz węzeł „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-157">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="96dcf-158">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="96dcf-158">Click Bind.</span></span>
    * <span data-ttu-id="96dcf-159">Utwórz wiersz podsumowania dla każdego zapamiętanego bloku.</span><span class="sxs-lookup"><span data-stu-id="96dcf-159">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="96dcf-160">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="96dcf-160">Click the Format tab.</span></span>
42. <span data-ttu-id="96dcf-161">W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków\Kod bloku”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-161">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="96dcf-162">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="96dcf-162">Click the Mapping tab.</span></span>
44. <span data-ttu-id="96dcf-163">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="96dcf-163">Click Edit formula.</span></span>
45. <span data-ttu-id="96dcf-164">W polu Formuła wpisz „"Identyfikator bloku: " & ”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-164">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="96dcf-165">"Identyfikator bloku: " &</span><span class="sxs-lookup"><span data-stu-id="96dcf-165">"Block id: " &</span></span>  
46. <span data-ttu-id="96dcf-166">W drzewie rozwiń węzeł „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-166">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="96dcf-167">W drzewie zaznacz element „$BlocksList\Wartość”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-167">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="96dcf-168">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="96dcf-168">Click Add data source.</span></span>
49. <span data-ttu-id="96dcf-169">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="96dcf-169">Click Save.</span></span>
50. <span data-ttu-id="96dcf-170">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="96dcf-170">Close the page.</span></span>
51. <span data-ttu-id="96dcf-171">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="96dcf-171">Click the Format tab.</span></span>
52. <span data-ttu-id="96dcf-172">W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków\Inwentaryzacja wierszy”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-172">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="96dcf-173">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="96dcf-173">Click the Mapping tab.</span></span>
54. <span data-ttu-id="96dcf-174">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="96dcf-174">Click Edit formula.</span></span>
    * <span data-ttu-id="96dcf-175">Utwórz dane wyjściowe dla liczby wierszy każdego bloku przedstawionej w tym raporcie.</span><span class="sxs-lookup"><span data-stu-id="96dcf-175">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="96dcf-176">W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & ”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-176">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="96dcf-177">"Liczba wierszy w tym bloku: " &</span><span class="sxs-lookup"><span data-stu-id="96dcf-177">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="96dcf-178">W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-178">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="96dcf-179">"Liczba wierszy w tym bloku: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="96dcf-179">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="96dcf-180">W drzewie zaznacz element „Funkcje gromadzenia danych\COUNTIFS”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-180">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="96dcf-181">Kliknij opcję Dodaj funkcję.</span><span class="sxs-lookup"><span data-stu-id="96dcf-181">Click Add function.</span></span>
59. <span data-ttu-id="96dcf-182">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="96dcf-182">Click Add data source.</span></span>
60. <span data-ttu-id="96dcf-183">W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', ”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-183">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="96dcf-184">"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="96dcf-184">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="96dcf-185">W drzewie rozwiń węzeł „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-185">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="96dcf-186">W drzewie zaznacz element „$BlocksList\Wartość”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-186">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="96dcf-187">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="96dcf-187">Click Add data source.</span></span>
64. <span data-ttu-id="96dcf-188">W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość, ”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-188">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="96dcf-189">"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość,</span><span class="sxs-lookup"><span data-stu-id="96dcf-189">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="96dcf-190">W drzewie zaznacz element „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-190">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="96dcf-191">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="96dcf-191">Click Add data source.</span></span>
67. <span data-ttu-id="96dcf-192">W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość, '$RecName', "\*"))”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-192">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="96dcf-193">"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="96dcf-193">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="96dcf-194">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="96dcf-194">Click Save.</span></span>
69. <span data-ttu-id="96dcf-195">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="96dcf-195">Close the page.</span></span>
70. <span data-ttu-id="96dcf-196">Kliknij kartę Format.</span><span class="sxs-lookup"><span data-stu-id="96dcf-196">Click the Format tab.</span></span>
71. <span data-ttu-id="96dcf-197">W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków\Łączna kwota”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-197">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="96dcf-198">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="96dcf-198">Click the Mapping tab.</span></span>
73. <span data-ttu-id="96dcf-199">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="96dcf-199">Click Edit formula.</span></span>
    * <span data-ttu-id="96dcf-200">Utwórz dane wyjściowe, który będą sumą kwot zafakturowanych dla wszystkich bloków przedstawionych w tym raporcie.</span><span class="sxs-lookup"><span data-stu-id="96dcf-200">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="96dcf-201">W polu Formuła wpisz „"Suma zafakturowanych kwot: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Wartość, '$RecName', "\*"))”.</span><span class="sxs-lookup"><span data-stu-id="96dcf-201">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="96dcf-202">"Suma zafakturowanych kwot: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Wartość, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="96dcf-202">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="96dcf-203">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="96dcf-203">Click Save.</span></span>
76. <span data-ttu-id="96dcf-204">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="96dcf-204">Close the page.</span></span>
77. <span data-ttu-id="96dcf-205">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="96dcf-205">Click Save.</span></span>
78. <span data-ttu-id="96dcf-206">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="96dcf-206">Close the page.</span></span>

