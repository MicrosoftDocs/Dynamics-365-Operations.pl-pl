--- 
title: "Uruchamianie formatów raportowania elektronicznego (ER) w celu wykonania zliczania i sumowania"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: c6d309416a3a0c4da07a76c90246f492585deef5
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="run-electronic-reporting-er-formats-to-do-counting-and-summing"></a><span data-ttu-id="e3f56-103">Uruchamianie formatów raportowania elektronicznego (ER) w celu wykonania zliczania i sumowania</span><span class="sxs-lookup"><span data-stu-id="e3f56-103">Run Electronic reporting (ER) formats to do counting and summing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e3f56-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="e3f56-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="e3f56-105">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="e3f56-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="e3f56-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 3: Używanie obliczeń do wygenerowania danych wyjściowych)”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 3: Use computations to make the output)” procedure.</span></span>

<span data-ttu-id="e3f56-107">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="e3f56-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="e3f56-108">Testowanie tej konfiguracji pod kątem generowania raportów Intrastat</span><span class="sxs-lookup"><span data-stu-id="e3f56-108">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="e3f56-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="e3f56-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="e3f56-110">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="e3f56-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="e3f56-111">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="e3f56-112">W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="e3f56-113">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="e3f56-114">W okienku akcji kliknij pozycję Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="e3f56-114">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="e3f56-115">Kliknij opcję Parametry użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e3f56-115">Click User parameters.</span></span>
8. <span data-ttu-id="e3f56-116">W polu Ustawienia uruchamiania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="e3f56-116">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="e3f56-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e3f56-117">Click OK.</span></span>
10. <span data-ttu-id="e3f56-118">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="e3f56-118">Click Edit.</span></span>
11. <span data-ttu-id="e3f56-119">W polu Uruchom wersję roboczą wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="e3f56-119">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="e3f56-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e3f56-120">Click Save.</span></span>
13. <span data-ttu-id="e3f56-121">Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Parametry handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="e3f56-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="e3f56-122">Rozwiń sekcję Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="e3f56-122">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="e3f56-123">Zaznacz konfigurację „Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-123">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
16. <span data-ttu-id="e3f56-124">Zaznacz konfigurację „Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-124">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
17. <span data-ttu-id="e3f56-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e3f56-125">Click Save.</span></span>
18. <span data-ttu-id="e3f56-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3f56-126">Close the page.</span></span>
19. <span data-ttu-id="e3f56-127">Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="e3f56-127">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="e3f56-128">Kliknij opcję Dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="e3f56-128">Click Output.</span></span>
21. <span data-ttu-id="e3f56-129">Kliknij przycisk Raport.</span><span class="sxs-lookup"><span data-stu-id="e3f56-129">Click Report.</span></span>
    * <span data-ttu-id="e3f56-130">Wykonaj proces generowania raportu Intrastat.</span><span class="sxs-lookup"><span data-stu-id="e3f56-130">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="e3f56-131">W polu Od dnia ustaw wartość daty równą „2000-01-01”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-131">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="e3f56-132">Zdefiniuj daty rozpoczęcia i zakończenia okresu sprawozdawczego obejmującego transakcje istniejące w formularzu.</span><span class="sxs-lookup"><span data-stu-id="e3f56-132">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="e3f56-133">W polu Do dnia ustaw wartość daty równą „2022-12-31”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-133">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="e3f56-134">Zdefiniuj daty rozpoczęcia i zakończenia okresu sprawozdawczego obejmującego transakcje istniejące w formularzu.</span><span class="sxs-lookup"><span data-stu-id="e3f56-134">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="e3f56-135">W polu Kierunek wybierz opcję „Przyjęcia”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-135">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="e3f56-136">W polu Generuj plik zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="e3f56-136">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="e3f56-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e3f56-137">Click OK.</span></span>
    * <span data-ttu-id="e3f56-138">Przejrzyj utworzone dane wyjściowe z wierszami podsumowania na końcu.</span><span class="sxs-lookup"><span data-stu-id="e3f56-138">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="e3f56-139">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e3f56-139">Click New.</span></span>
28. <span data-ttu-id="e3f56-140">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="e3f56-140">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="e3f56-141">W polu Kierunek wybierz opcję „Wysyłki”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-141">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="e3f56-142">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e3f56-142">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="e3f56-143">W polu Asortyment wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e3f56-143">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="e3f56-144">W polu Waga ustaw wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-144">Set Weight to '10'.</span></span>
33. <span data-ttu-id="e3f56-145">W polu Kwota faktury ustaw wartość „10000”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-145">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="e3f56-146">W polu Kwota statystyczna ustaw wartość „10000”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-146">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="e3f56-147">Kliknij opcję Dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="e3f56-147">Click Output.</span></span>
36. <span data-ttu-id="e3f56-148">Kliknij przycisk Raport.</span><span class="sxs-lookup"><span data-stu-id="e3f56-148">Click Report.</span></span>
37. <span data-ttu-id="e3f56-149">W polu Kierunek wybierz opcję „Wysyłki”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-149">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="e3f56-150">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e3f56-150">Click OK.</span></span>
    * <span data-ttu-id="e3f56-151">Przejrzyj utworzone dane wyjściowe z wierszami podsumowania na końcu.</span><span class="sxs-lookup"><span data-stu-id="e3f56-151">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="e3f56-152">Należy zauważyć, że zmieniły się one w porównaniu z pierwszą sesją.</span><span class="sxs-lookup"><span data-stu-id="e3f56-152">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="e3f56-153">Uruchomienie tej konfiguracji w trybie debugowania w celu przejrzenia zebranych danych inwentaryzacji i sumowania</span><span class="sxs-lookup"><span data-stu-id="e3f56-153">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="e3f56-154">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="e3f56-154">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="e3f56-155">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-155">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="e3f56-156">W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-156">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="e3f56-157">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-157">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="e3f56-158">W okienku akcji kliknij pozycję Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="e3f56-158">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="e3f56-159">Kliknij opcję Parametry użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e3f56-159">Click User parameters.</span></span>
7. <span data-ttu-id="e3f56-160">W polu Uruchom w trybie debugowania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="e3f56-160">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="e3f56-161">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e3f56-161">Click OK.</span></span>
9. <span data-ttu-id="e3f56-162">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3f56-162">Close the page.</span></span>
10. <span data-ttu-id="e3f56-163">Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="e3f56-163">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="e3f56-164">Kliknij opcję Dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="e3f56-164">Click Output.</span></span>
12. <span data-ttu-id="e3f56-165">Kliknij przycisk Raport.</span><span class="sxs-lookup"><span data-stu-id="e3f56-165">Click Report.</span></span>
13. <span data-ttu-id="e3f56-166">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e3f56-166">Click OK.</span></span>
14. <span data-ttu-id="e3f56-167">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3f56-167">Close the page.</span></span>
15. <span data-ttu-id="e3f56-168">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="e3f56-168">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="e3f56-169">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-169">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="e3f56-170">W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-170">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="e3f56-171">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.</span><span class="sxs-lookup"><span data-stu-id="e3f56-171">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="e3f56-172">Kliknij opcję Dzienniki debugowania.</span><span class="sxs-lookup"><span data-stu-id="e3f56-172">Click Debug logs.</span></span>
    * <span data-ttu-id="e3f56-173">Należy zauważyć, że utworzono rekord dziennika debugowania dla procesu wykonywania wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="e3f56-173">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="e3f56-174">Kliknij opcję Dołącz.</span><span class="sxs-lookup"><span data-stu-id="e3f56-174">Click Attach.</span></span>
21. <span data-ttu-id="e3f56-175">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="e3f56-175">Click Open.</span></span>
    * <span data-ttu-id="e3f56-176">Przejrzyj utworzony plik XML zawierający szczegóły inwentaryzacji i sumowania, które zostały zebrane podczas wykonywania wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="e3f56-176">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  


