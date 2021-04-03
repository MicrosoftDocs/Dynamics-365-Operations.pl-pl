---
title: ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 4 — Inicjowanie formatu)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego do zliczania i sumowania na podstawie danych już wygenerowanego tekstu wyjściowego. (część 4)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ca8449581edc06016b6e387880aad91087b67f1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565424"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a><span data-ttu-id="51d6d-104">ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 4 — Inicjowanie formatu)</span><span class="sxs-lookup"><span data-stu-id="51d6d-104">ER Configure format to do counting and summing (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="51d6d-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="51d6d-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="51d6d-106">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="51d6d-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="51d6d-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 3: Używanie obliczeń do wygenerowania danych wyjściowych)”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 3: Use computations to make the output)" procedure.</span></span>

<span data-ttu-id="51d6d-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="51d6d-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="51d6d-109">Testowanie tej konfiguracji pod kątem generowania raportów Intrastat</span><span class="sxs-lookup"><span data-stu-id="51d6d-109">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="51d6d-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="51d6d-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="51d6d-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="51d6d-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="51d6d-112">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="51d6d-113">W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="51d6d-114">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="51d6d-115">W okienku akcji kliknij pozycję Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="51d6d-115">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="51d6d-116">Kliknij opcję Parametry użytkownika.</span><span class="sxs-lookup"><span data-stu-id="51d6d-116">Click User parameters.</span></span>
8. <span data-ttu-id="51d6d-117">W polu Ustawienia uruchamiania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="51d6d-117">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="51d6d-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51d6d-118">Click OK.</span></span>
10. <span data-ttu-id="51d6d-119">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="51d6d-119">Click Edit.</span></span>
11. <span data-ttu-id="51d6d-120">W polu Uruchom wersję roboczą wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="51d6d-120">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="51d6d-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="51d6d-121">Click Save.</span></span>
13. <span data-ttu-id="51d6d-122">Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Parametry handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="51d6d-122">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="51d6d-123">Rozwiń sekcję Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="51d6d-123">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="51d6d-124">Zaznacz konfigurację „Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-124">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
16. <span data-ttu-id="51d6d-125">Zaznacz konfigurację „Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-125">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
17. <span data-ttu-id="51d6d-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="51d6d-126">Click Save.</span></span>
18. <span data-ttu-id="51d6d-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="51d6d-127">Close the page.</span></span>
19. <span data-ttu-id="51d6d-128">Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="51d6d-128">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="51d6d-129">Kliknij opcję Dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="51d6d-129">Click Output.</span></span>
21. <span data-ttu-id="51d6d-130">Kliknij przycisk Raport.</span><span class="sxs-lookup"><span data-stu-id="51d6d-130">Click Report.</span></span>
    * <span data-ttu-id="51d6d-131">Wykonaj proces generowania raportu Intrastat.</span><span class="sxs-lookup"><span data-stu-id="51d6d-131">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="51d6d-132">W polu Od dnia ustaw wartość daty równą „2000-01-01”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-132">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="51d6d-133">Zdefiniuj daty rozpoczęcia i zakończenia okresu sprawozdawczego obejmującego transakcje istniejące w formularzu.</span><span class="sxs-lookup"><span data-stu-id="51d6d-133">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="51d6d-134">W polu Do dnia ustaw wartość daty równą „2022-12-31”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-134">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="51d6d-135">Zdefiniuj daty rozpoczęcia i zakończenia okresu sprawozdawczego obejmującego transakcje istniejące w formularzu.</span><span class="sxs-lookup"><span data-stu-id="51d6d-135">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="51d6d-136">W polu Kierunek wybierz opcję „Przyjęcia”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-136">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="51d6d-137">W polu Generuj plik zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="51d6d-137">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="51d6d-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51d6d-138">Click OK.</span></span>
    * <span data-ttu-id="51d6d-139">Przejrzyj utworzone dane wyjściowe z wierszami podsumowania na końcu.</span><span class="sxs-lookup"><span data-stu-id="51d6d-139">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="51d6d-140">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="51d6d-140">Click New.</span></span>
28. <span data-ttu-id="51d6d-141">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="51d6d-141">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="51d6d-142">W polu Kierunek wybierz opcję „Wysyłki”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-142">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="51d6d-143">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="51d6d-143">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="51d6d-144">W polu Asortyment wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="51d6d-144">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="51d6d-145">W polu Waga ustaw wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-145">Set Weight to '10'.</span></span>
33. <span data-ttu-id="51d6d-146">W polu Kwota faktury ustaw wartość „10000”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-146">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="51d6d-147">W polu Kwota statystyczna ustaw wartość „10000”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-147">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="51d6d-148">Kliknij opcję Dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="51d6d-148">Click Output.</span></span>
36. <span data-ttu-id="51d6d-149">Kliknij przycisk Raport.</span><span class="sxs-lookup"><span data-stu-id="51d6d-149">Click Report.</span></span>
37. <span data-ttu-id="51d6d-150">W polu Kierunek wybierz opcję „Wysyłki”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-150">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="51d6d-151">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51d6d-151">Click OK.</span></span>
    * <span data-ttu-id="51d6d-152">Przejrzyj utworzone dane wyjściowe z wierszami podsumowania na końcu.</span><span class="sxs-lookup"><span data-stu-id="51d6d-152">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="51d6d-153">Należy zauważyć, że zmieniły się one w porównaniu z pierwszą sesją.</span><span class="sxs-lookup"><span data-stu-id="51d6d-153">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="51d6d-154">Uruchomienie tej konfiguracji w trybie debugowania w celu przejrzenia zebranych danych inwentaryzacji i sumowania</span><span class="sxs-lookup"><span data-stu-id="51d6d-154">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="51d6d-155">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="51d6d-155">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="51d6d-156">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-156">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="51d6d-157">W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-157">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="51d6d-158">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-158">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="51d6d-159">W okienku akcji kliknij pozycję Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="51d6d-159">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="51d6d-160">Kliknij opcję Parametry użytkownika.</span><span class="sxs-lookup"><span data-stu-id="51d6d-160">Click User parameters.</span></span>
7. <span data-ttu-id="51d6d-161">W polu Uruchom w trybie debugowania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="51d6d-161">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="51d6d-162">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51d6d-162">Click OK.</span></span>
9. <span data-ttu-id="51d6d-163">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="51d6d-163">Close the page.</span></span>
10. <span data-ttu-id="51d6d-164">Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="51d6d-164">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="51d6d-165">Kliknij opcję Dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="51d6d-165">Click Output.</span></span>
12. <span data-ttu-id="51d6d-166">Kliknij przycisk Raport.</span><span class="sxs-lookup"><span data-stu-id="51d6d-166">Click Report.</span></span>
13. <span data-ttu-id="51d6d-167">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51d6d-167">Click OK.</span></span>
14. <span data-ttu-id="51d6d-168">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="51d6d-168">Close the page.</span></span>
15. <span data-ttu-id="51d6d-169">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="51d6d-169">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="51d6d-170">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-170">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="51d6d-171">W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-171">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="51d6d-172">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="51d6d-172">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="51d6d-173">Kliknij opcję Dzienniki debugowania.</span><span class="sxs-lookup"><span data-stu-id="51d6d-173">Click Debug logs.</span></span>
    * <span data-ttu-id="51d6d-174">Należy zauważyć, że utworzono rekord dziennika debugowania dla procesu wykonywania wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="51d6d-174">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="51d6d-175">Kliknij opcję Dołącz.</span><span class="sxs-lookup"><span data-stu-id="51d6d-175">Click Attach.</span></span>
21. <span data-ttu-id="51d6d-176">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="51d6d-176">Click Open.</span></span>
    * <span data-ttu-id="51d6d-177">Przejrzyj utworzony plik XML zawierający szczegóły inwentaryzacji i sumowania, które zostały zebrane podczas wykonywania wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="51d6d-177">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]