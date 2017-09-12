--- 
title: Generowanie unijnej deklaracji Intrastat
description: "Ta procedura przeprowadzi przez kolejne czynności, które należy wykonać, aby wyeksportować deklarację Intrastat w formacie pliku elektronicznego i przejrzeć dane deklaracji w formacie programu Excel."
author: Anasyash
manager: AnnBe
ms.date: 06/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f74da78232c477224c8fa753e9755b7f9d13174d
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="generate-an-eu-intrastat-declaration"></a><span data-ttu-id="b1e6a-103">Generowanie unijnej deklaracji Intrastat</span><span class="sxs-lookup"><span data-stu-id="b1e6a-103">Generate an EU Intrastat declaration</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b1e6a-104">Ta procedura przeprowadzi przez kolejne czynności, które należy wykonać, aby wyeksportować deklarację Intrastat w formacie pliku elektronicznego i przejrzeć dane deklaracji w formacie programu Excel.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-104">This procedure walks you through the steps required to export the Intrastat declaration in the electronic file format and preview the declaration data in an Excel format.</span></span> 

<span data-ttu-id="b1e6a-105">Aby można było wykonać tę procedurę, należy przenieść transakcje do systemu Intrastat.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-105">Before you can complete this procedure, you must transfer transactions to the Intrastat.</span></span> 

<span data-ttu-id="b1e6a-106">Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-106">This procedure was created using the demo data company DEMF.</span></span>


## <a name="import-configurations-with-settings"></a><span data-ttu-id="b1e6a-107">Importowanie konfiguracji z ustawieniami</span><span class="sxs-lookup"><span data-stu-id="b1e6a-107">Import configurations with settings</span></span>
1. <span data-ttu-id="b1e6a-108">Wybierz kolejno opcje Obszary robocze > Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="b1e6a-108">Go to Workspaces > Electronic reporting</span></span>
2. <span data-ttu-id="b1e6a-109">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-109">Click Set active.</span></span>
3. <span data-ttu-id="b1e6a-110">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-110">Click Repositories.</span></span>
4. <span data-ttu-id="b1e6a-111">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-111">Click Open.</span></span>
5. <span data-ttu-id="b1e6a-112">Otwórz filtr kolumny Nazwa konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-112">Open Configuration name column filter.</span></span>
6. <span data-ttu-id="b1e6a-113">Zastosuj filtr w polu „Nazwa konfiguracji” z wartości „Intrastat (DE)”, używając operatora filtru „zaczyna się od”.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-113">Apply a filter on the "Configuration name" field, with a value of "Intrastat (DE)", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="b1e6a-114">Wybierz nazwę konfiguracji mającą zastosowanie do kraju firmy.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-114">You should select the configuration name applicable for the country of your legal entity.</span></span> <span data-ttu-id="b1e6a-115">Ta procedura wykorzystuje przykładową firmę niemiecką (DEMF), dlatego należy wybrać opcję „Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-115">This procedure uses the German legal entity (DEMF) as an example, therefore "Intrastat (DE)" should be chosen.</span></span>  
    * <span data-ttu-id="b1e6a-116">Kliknij kolejno przyciski Importuj i Tak.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-116">Click Import and then click Yes.</span></span>  
7. <span data-ttu-id="b1e6a-117">Otwórz filtr kolumny Nazwa konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-117">Open Configuration name column filter.</span></span>
8. <span data-ttu-id="b1e6a-118">Zastosuj filtr w polu „Nazwa konfiguracji” z wartości „raport intrastat”, używając operatora filtru „zaczyna się od”.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-118">Apply a filter on the "Configuration name" field, with a value of "intrastat report", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="b1e6a-119">Kliknij kolejno przyciski Importuj i Tak.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-119">Click Import and then click Yes.</span></span>  

## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="b1e6a-120">Konfigurowanie parametrów handlu zagranicznego</span><span class="sxs-lookup"><span data-stu-id="b1e6a-120">Set up Foreign trade parameters</span></span>
1. <span data-ttu-id="b1e6a-121">Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Parametry handlu zagranicznego</span><span class="sxs-lookup"><span data-stu-id="b1e6a-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
2. <span data-ttu-id="b1e6a-122">Rozwiń sekcję Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-122">Expand the Electronic reporting section.</span></span>
3. <span data-ttu-id="b1e6a-123">W polu Mapowanie formatu plików wprowadź lub wybierz wartość Intrastat (DE).</span><span class="sxs-lookup"><span data-stu-id="b1e6a-123">In the File format mapping field, enter or select a value Intrastat (DE)</span></span>
4. <span data-ttu-id="b1e6a-124">W polu Mapowanie formatu raportów wprowadź lub wybierz wartość Raport Intrastat.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-124">In the Report format mapping field, enter or select a value Intrastat report</span></span>
5. <span data-ttu-id="b1e6a-125">Rozwiń sekcję Reguły zaokrąglania.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-125">Expand the Rounding rules section.</span></span>
    * <span data-ttu-id="b1e6a-126">Należy skonfigurować reguły zaokrąglania, które mają zastosowanie w danym kraju/regionie na potrzeby raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-126">You should set up rounding rules that are applicable in your country/region for Intrastat reporting.</span></span>  
6. <span data-ttu-id="b1e6a-127">W polu Reguła zaokrąglania wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-127">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="b1e6a-128">Wprowadź dokładność zaokrąglania, na przykład „0,01”.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-128">Enter rounding precision, for example, enter '0.01'.</span></span>  
7. <span data-ttu-id="b1e6a-129">W polu Liczba miejsc dziesiętnych kwoty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-129">In the Number of decimals for amount field, enter a number.</span></span>
    * <span data-ttu-id="b1e6a-130">Na przykład wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-130">For example, enter '2'.</span></span>  
8. <span data-ttu-id="b1e6a-131">W polu Zaokrąglanie poniżej 1 kg wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-131">In the Rounding below 1 kg field, select an option.</span></span>
    * <span data-ttu-id="b1e6a-132">Na przykład wybierz opcję „Zaokrąglanie do 1 kg”.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-132">For example, select 'Rounding up to 1 kg'.</span></span>  
9. <span data-ttu-id="b1e6a-133">W polu Reguła zaokrąglania wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-133">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="b1e6a-134">Na przykład wpisz „1”, aby zaokrąglać wagę do liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-134">For example, enter '1' for rounding weight to the integer.</span></span>  
10. <span data-ttu-id="b1e6a-135">Rozwiń sekcję Dolny limit.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-135">Expand the Minimum limit section.</span></span>
11. <span data-ttu-id="b1e6a-136">W polu Waga wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-136">In the Weight field, enter a number.</span></span>
    * <span data-ttu-id="b1e6a-137">Na przykład wpisz „10” jako minimalną wagę.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-137">For example, enter '10' as the minimum weight.</span></span>  
12. <span data-ttu-id="b1e6a-138">W polu Kwota wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-138">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="b1e6a-139">Na przykład wpisz „200” jako minimalną kwotę.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-139">For example, enter '200' as the minimum amount.</span></span>  
13. <span data-ttu-id="b1e6a-140">W polu Asortyment wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-140">In the Commodity field, enter or select a value.</span></span>

## <a name="set-up-compression-of-intrastat"></a><span data-ttu-id="b1e6a-141">Ustawianie kompresji Intrastat</span><span class="sxs-lookup"><span data-stu-id="b1e6a-141">Set up Compression of Intrastat</span></span>
1. <span data-ttu-id="b1e6a-142">Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Kompresja Intrastat.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-142">Go to Tax > Setup > Foreign trade > Compression of Intrastat.</span></span>
2. <span data-ttu-id="b1e6a-143">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-143">Click Remove.</span></span>
3. <span data-ttu-id="b1e6a-144">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b1e6a-145">Na przykład w sekcji Dostępne wybierz asortyment.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-145">For example, select Commodity in the Available section.</span></span>  
4. <span data-ttu-id="b1e6a-146">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-146">Click Add.</span></span>

## <a name="generate-intrastat-declaration"></a><span data-ttu-id="b1e6a-147">Generowanie deklaracji Intrastat</span><span class="sxs-lookup"><span data-stu-id="b1e6a-147">Generate Intrastat declaration</span></span>
1. <span data-ttu-id="b1e6a-148">Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat</span><span class="sxs-lookup"><span data-stu-id="b1e6a-148">Go to Tax > Declarations > Foreign trade > Intrastat</span></span>
2. <span data-ttu-id="b1e6a-149">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-149">Click Validate.</span></span>
    * <span data-ttu-id="b1e6a-150">Sprawdzanie poprawności odbywa się zgodnie z zawartością pola Sprawdzenie ustawień na stronie Parametry handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-150">The validation is done according to the Check setup field on the Foreign trade parameters page.</span></span>  
3. <span data-ttu-id="b1e6a-151">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-151">Click OK.</span></span>
4. <span data-ttu-id="b1e6a-152">Kliknij przycisk Aktualizuj.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-152">Click Update.</span></span>
5. <span data-ttu-id="b1e6a-153">Kliknij opcję Dolny limit.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-153">Click Minimum limit.</span></span>
6. <span data-ttu-id="b1e6a-154">W polu Data początkowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-154">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="b1e6a-155">Na przykład wpisz 1 stycznia 2015 r.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-155">For example, enter January 1, 2015.</span></span>  
7. <span data-ttu-id="b1e6a-156">W polu Kompresuj wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-156">Select Yes in the Compress field.</span></span>
8. <span data-ttu-id="b1e6a-157">W polu Data końcowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-157">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="b1e6a-158">Na przykład wpisz 31 stycznia 2015 r.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-158">For example, enter January 31, 2015.</span></span>  
9. <span data-ttu-id="b1e6a-159">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-159">Click OK.</span></span>
10. <span data-ttu-id="b1e6a-160">Kliknij przycisk Aktualizuj.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-160">Click Update.</span></span>
11. <span data-ttu-id="b1e6a-161">Kliknij opcję Kompresuj.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-161">Click Compress.</span></span>
    * <span data-ttu-id="b1e6a-162">Ta kompresja odbywa się zgodnie z konfiguracją kompresji ustawień raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-162">This compression happens according to how you set the Compression of intrastate settings.</span></span>  
12. <span data-ttu-id="b1e6a-163">W polu Data początkowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-163">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="b1e6a-164">Na przykład wpisz 1 stycznia 2015 r.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-164">For example, enter January 1, 2015.</span></span>  
13. <span data-ttu-id="b1e6a-165">W polu Data końcowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-165">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="b1e6a-166">Na przykład wpisz 31 stycznia 2015 r.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-166">For example, enter 31st January 2015.</span></span>  
14. <span data-ttu-id="b1e6a-167">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-167">Click OK.</span></span>
15. <span data-ttu-id="b1e6a-168">Kliknij przycisk Aktualizuj.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-168">Click Update.</span></span>
16. <span data-ttu-id="b1e6a-169">Kliknij opcję Ponowne generowanie numerów sekwencyjnych.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-169">Click Regenerate sequence numbers.</span></span>
17. <span data-ttu-id="b1e6a-170">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-170">Click OK.</span></span>
18. <span data-ttu-id="b1e6a-171">Kliknij opcję Dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-171">Click Output.</span></span>
19. <span data-ttu-id="b1e6a-172">Kliknij przycisk Raport.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-172">Click Report.</span></span>
20. <span data-ttu-id="b1e6a-173">W polu Od dnia wprowadź pierwszy dzień okresu raportowania.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-173">In the From date field, enter the first date of the reporting period.</span></span>
    * <span data-ttu-id="b1e6a-174">Na przykład ustaw datę 1 stycznia 2015 r.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-174">For example, set the date to January 1, 2015.</span></span>  
21. <span data-ttu-id="b1e6a-175">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-175">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="b1e6a-176">Na przykład wpisz 31 stycznia 2015 r.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-176">For example, enter January 31, 2015.</span></span>  
22. <span data-ttu-id="b1e6a-177">W polu Generuj plik zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-177">Select Yes in the Generate file field.</span></span>
23. <span data-ttu-id="b1e6a-178">W polu Nazwa pliku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-178">In the File name field, type a value.</span></span>
24. <span data-ttu-id="b1e6a-179">W polu Generuj raport zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-179">Select Yes in the Generate report field.</span></span>
25. <span data-ttu-id="b1e6a-180">W polu Nazwa pliku raportu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-180">In the Report file name field, type a value.</span></span>
26. <span data-ttu-id="b1e6a-181">W polu Kierunek wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-181">In the Direction field, select an option.</span></span>
    * <span data-ttu-id="b1e6a-182">Na przykład wybierz opcję „Wysyłki”.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-182">For example, select 'Dispatches'.</span></span>  
27. <span data-ttu-id="b1e6a-183">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-183">Click OK.</span></span>


