--- 
title: "Przeglądanie konfiguracji w celu tworzenia raportów w formatach pakietu Microsoft Office z osadzonymi obrazami"
description: "Aby wykonać te kroki, należy najpierw wykonać kroki z przewodnika po zadaniu „ER Tworzenie raportów w formatach programu MS Office z osadzonymi obrazami (Część 1 — Konfigurowanie parametrów)”."
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fe58809c60fa27a605d84a61893ff569ded058ef
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="review-configurations-to-make-reports-in-microsoft-office-formats-with-embedded-images"></a><span data-ttu-id="28784-103">Przeglądanie konfiguracji w celu tworzenia raportów w formatach pakietu Microsoft Office z osadzonymi obrazami</span><span class="sxs-lookup"><span data-stu-id="28784-103">Review configurations to make reports in Microsoft Office formats with embedded images</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="28784-104">Aby wykonać te kroki, należy najpierw wykonać kroki z przewodnika po zadaniu „ER Tworzenie raportów w formatach programu MS Office z osadzonymi obrazami (Część 1: Konfigurowanie parametrów)”.</span><span class="sxs-lookup"><span data-stu-id="28784-104">To complete these steps, you must first complete the steps in the “ER Make reports in MS Office formats with embedded images (Part 1: Set up parameters)” task guide.</span></span>

<span data-ttu-id="28784-105">W tej procedurze pokazano sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentów elektronicznych z osadzonymi obrazami w programach Microsoft Excel i Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="28784-105">This procedure shows how to design Electronic reporting (ER) configurations to generate electronic documents that contain embedded images in Microsoft Excel and Microsoft Word.</span></span> <span data-ttu-id="28784-106">W tym przykładzie przejrzysz konfiguracje ER przykładowej firmy Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="28784-106">In this example, you will review ER configurations for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="28784-107">Ta procedura jest przeznaczona dla użytkowników z przypisaną rola Administrator systemu lub Deweloper raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="28784-107">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="28784-108">Kroki można wykonać przy użyciu zestawu danych firmy USMF.</span><span class="sxs-lookup"><span data-stu-id="28784-108">The steps can be completed by using the USMF data set.</span></span>


## <a name="review-the-imported-data-model"></a><span data-ttu-id="28784-109">Przeglądanie zaimportowanego modelu danych</span><span class="sxs-lookup"><span data-stu-id="28784-109">Review the imported data model</span></span>
1. <span data-ttu-id="28784-110">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="28784-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="28784-111">W drzewie zaznacz element „Model czeków”.</span><span class="sxs-lookup"><span data-stu-id="28784-111">In the tree, select 'Model for cheques'.</span></span>
3. <span data-ttu-id="28784-112">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="28784-112">Click Designer.</span></span>
    * <span data-ttu-id="28784-113">Ten model jest przeznaczony do reprezentowania czeków płatniczych z biznesowego punktu widzenia oraz do mapowanie tego modelu na źródła danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="28784-113">This model is designed to represent payment cheques from the business standpoint and the mapping of this model to the application’s data sources.</span></span> <span data-ttu-id="28784-114">Model musi zostać przejrzany przez projektanta operacji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="28784-114">Review this model by the ER Operations designer.</span></span> <span data-ttu-id="28784-115">Należy zwrócić uwagę na atrybuty prezentowanych elementów modelu: struktura, nazwa, opis, typ danych i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="28784-115">Note the attributes of the model elements that are presented: structure, name, description, data type, and so on.</span></span>   
4. <span data-ttu-id="28784-116">W drzewie rozwiń węzeł „katalog główny”.</span><span class="sxs-lookup"><span data-stu-id="28784-116">In the tree, expand 'root'.</span></span>
5. <span data-ttu-id="28784-117">W drzewie zaznacz element „katalog główny\czeki”.</span><span class="sxs-lookup"><span data-stu-id="28784-117">In the tree, select 'root\cheques'.</span></span>
6. <span data-ttu-id="28784-118">W drzewie rozwiń węzeł „katalog główny\czeki”.</span><span class="sxs-lookup"><span data-stu-id="28784-118">In the tree, expand 'root\cheques'.</span></span>
7. <span data-ttu-id="28784-119">W drzewie rozwiń węzeł „katalog główny\czeki\atrybuty”.</span><span class="sxs-lookup"><span data-stu-id="28784-119">In the tree, expand 'root\cheques\attributes'.</span></span>
8. <span data-ttu-id="28784-120">W drzewie rozwiń węzeł „katalog główny\płatnik”.</span><span class="sxs-lookup"><span data-stu-id="28784-120">In the tree, expand 'root\payer'.</span></span>
9. <span data-ttu-id="28784-121">W drzewie zaznacz element „katalog główny\istestrun”.</span><span class="sxs-lookup"><span data-stu-id="28784-121">In the tree, select 'root\istestrun'.</span></span>
10. <span data-ttu-id="28784-122">W drzewie zaznacz element „katalog główny\układ”.</span><span class="sxs-lookup"><span data-stu-id="28784-122">In the tree, select 'root\layout'.</span></span>
    * <span data-ttu-id="28784-123">Element układu tego modelu reprezentuje szczegóły układu formularza drukowania czeków dla wybranego konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="28784-123">The layout element of this model represents the details of the printing cheque form layout for the selected bank account.</span></span> <span data-ttu-id="28784-124">Zawiera także dwa węzły danych typu Kontener do przechowywania obrazów.</span><span class="sxs-lookup"><span data-stu-id="28784-124">It also includes two nodes of the Container data type to store images.</span></span>   
11. <span data-ttu-id="28784-125">W drzewie rozwiń węzeł „katalog główny\układ”.</span><span class="sxs-lookup"><span data-stu-id="28784-125">In the tree, expand 'root\layout'.</span></span>
12. <span data-ttu-id="28784-126">W drzewie zaznacz element „katalog główny\układ\logo firmy”.</span><span class="sxs-lookup"><span data-stu-id="28784-126">In the tree, select 'root\layout\company logo'.</span></span>
13. <span data-ttu-id="28784-127">W drzewie rozwiń węzeł „katalog główny\układ\logo firmy”.</span><span class="sxs-lookup"><span data-stu-id="28784-127">In the tree, expand 'root\layout\company logo'.</span></span>
14. <span data-ttu-id="28784-128">W drzewie zaznacz element „katalog główny\układ\logo firmy\obraz”.</span><span class="sxs-lookup"><span data-stu-id="28784-128">In the tree, select 'root\layout\company logo\image'.</span></span>
15. <span data-ttu-id="28784-129">W drzewie zaznacz element „katalog główny\układ\logo firmy\isprinted”.</span><span class="sxs-lookup"><span data-stu-id="28784-129">In the tree, select 'root\layout\company logo\isprinted'.</span></span>
16. <span data-ttu-id="28784-130">W drzewie zaznacz element „katalog główny\układ\podpis”.</span><span class="sxs-lookup"><span data-stu-id="28784-130">In the tree, select 'root\layout\signature'.</span></span>
17. <span data-ttu-id="28784-131">W drzewie rozwiń węzeł „katalog główny\układ\podpis”.</span><span class="sxs-lookup"><span data-stu-id="28784-131">In the tree, expand 'root\layout\signature'.</span></span>
18. <span data-ttu-id="28784-132">W drzewie zaznacz element „katalog główny\układ\podpis\obraz”.</span><span class="sxs-lookup"><span data-stu-id="28784-132">In the tree, select 'root\layout\signature\image'.</span></span>
19. <span data-ttu-id="28784-133">W drzewie zaznacz element „katalog główny\układ\podpis\isprinted”.</span><span class="sxs-lookup"><span data-stu-id="28784-133">In the tree, select 'root\layout\signature\isprinted'.</span></span>
    * <span data-ttu-id="28784-134">Należy zauważyć, że dwa elementy modelu danych obrazu są powiązane z polami tabel zawierających obrazy logo firmy i podpisu osoby upoważnionej osoby w formacie binarnym.</span><span class="sxs-lookup"><span data-stu-id="28784-134">Note that two image data model elements are bound to the fields of the tables that contain images of the company logo and the authorized person’s signature in binary format.</span></span>  
20. <span data-ttu-id="28784-135">W drzewie rozwiń węzeł „katalog główny\układ\znak wodny”.</span><span class="sxs-lookup"><span data-stu-id="28784-135">In the tree, expand 'root\layout\watermark'.</span></span>
21. <span data-ttu-id="28784-136">Kliknij opcję Mapuj model na źródło danych.</span><span class="sxs-lookup"><span data-stu-id="28784-136">Click Map model to datasource.</span></span>
22. <span data-ttu-id="28784-137">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="28784-137">Click Designer.</span></span>
23. <span data-ttu-id="28784-138">W drzewie rozwiń węzeł „chequesselected”.</span><span class="sxs-lookup"><span data-stu-id="28784-138">In the tree, expand 'chequesselected'.</span></span>
24. <span data-ttu-id="28784-139">W drzewie rozwiń węzeł „układ”.</span><span class="sxs-lookup"><span data-stu-id="28784-139">In the tree, expand 'layout'.</span></span>
25. <span data-ttu-id="28784-140">W drzewie rozwiń węzeł „układ\logo firmy”.</span><span class="sxs-lookup"><span data-stu-id="28784-140">In the tree, expand 'layout\company logo'.</span></span>
26. <span data-ttu-id="28784-141">W drzewie rozwiń węzeł „układ\podpis”.</span><span class="sxs-lookup"><span data-stu-id="28784-141">In the tree, expand 'layout\signature'.</span></span>
27. <span data-ttu-id="28784-142">W drzewie rozwiń węzeł „układ\znak wodny”.</span><span class="sxs-lookup"><span data-stu-id="28784-142">In the tree, expand 'layout\watermark'.</span></span>
28. <span data-ttu-id="28784-143">Włącz opcję „Pokaż szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="28784-143">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="28784-144">Należy zauważyć, że element modelu danych czeków jest powiązany z tabelą TmpChequePrintout, która w czasie wykonywania będzie zawierała rekordy czeków wybranych przez użytkownika do drukowania.</span><span class="sxs-lookup"><span data-stu-id="28784-144">Note that the cheques data model element is bound to the TmpChequePrintout table that, at runtime, will contain records for cheques that the user has selected for printing.</span></span>   
29. <span data-ttu-id="28784-145">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="28784-145">Close the page.</span></span>
30. <span data-ttu-id="28784-146">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="28784-146">Close the page.</span></span>
31. <span data-ttu-id="28784-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="28784-147">Close the page.</span></span>

## <a name="review-the-imported-format"></a><span data-ttu-id="28784-148">Przeglądanie zaimportowanego formatu</span><span class="sxs-lookup"><span data-stu-id="28784-148">Review the imported format</span></span>
1. <span data-ttu-id="28784-149">W drzewie rozwiń węzeł „Model czeków”.</span><span class="sxs-lookup"><span data-stu-id="28784-149">In the tree, expand 'Model for cheques'.</span></span>
2. <span data-ttu-id="28784-150">W drzewie zaznacz element „Model czeków\Format drukowania czeków”.</span><span class="sxs-lookup"><span data-stu-id="28784-150">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
3. <span data-ttu-id="28784-151">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="28784-151">Click Designer.</span></span>
4. <span data-ttu-id="28784-152">Kliknij opcję Załączniki.</span><span class="sxs-lookup"><span data-stu-id="28784-152">Click Attachments.</span></span>
5. <span data-ttu-id="28784-153">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="28784-153">Click Open.</span></span>
    * <span data-ttu-id="28784-154">Otwórz szablon dołączonego raportu w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="28784-154">Open the attached report’s template in Excel.</span></span>  
    * <span data-ttu-id="28784-155">Przejrzyj szablon programu Excel dołączonego raportu, który będzie używany do drukowania czeków.</span><span class="sxs-lookup"><span data-stu-id="28784-155">Review the attached report’s Excel template that will be used to print cheques.</span></span> <span data-ttu-id="28784-156">Szablon zawiera dwa czeki na każdej stronie i jest przeznaczony do drukowania czeków na formularzu z nadrukiem.</span><span class="sxs-lookup"><span data-stu-id="28784-156">The template contains two cheques per page and is designed to print cheques to the preprinted form.</span></span> <span data-ttu-id="28784-157">Należy zauważyć, że dwa puste obrazy są osadzone.</span><span class="sxs-lookup"><span data-stu-id="28784-157">Note that two blank images are embedded.</span></span> <span data-ttu-id="28784-158">Te puste obrazy są przeznaczone na logo firmy i podpis osoby, która autoryzuje płatność.</span><span class="sxs-lookup"><span data-stu-id="28784-158">These blank images are for the company logo and the signature of the person who is authorizing a payment.</span></span> <span data-ttu-id="28784-159">Upewnij się, że w programie Excel obrazy mają nazwy odpowiednio CompLogo i SignatureImage.</span><span class="sxs-lookup"><span data-stu-id="28784-159">Verify that the images are named CompLogo and SignatureImage, respectively, in Excel.</span></span>   
6. <span data-ttu-id="28784-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="28784-160">Close the page.</span></span>
7. <span data-ttu-id="28784-161">W drzewie rozwiń węzeł „Raport”.</span><span class="sxs-lookup"><span data-stu-id="28784-161">In the tree, expand 'Report'.</span></span>
8. <span data-ttu-id="28784-162">W drzewie rozwiń węzeł „Raport\ChequeLines”.</span><span class="sxs-lookup"><span data-stu-id="28784-162">In the tree, expand 'Report\ChequeLines'.</span></span>
9. <span data-ttu-id="28784-163">W drzewie zaznacz element „Raport\ChequeLines\CompLogo”.</span><span class="sxs-lookup"><span data-stu-id="28784-163">In the tree, select 'Report\ChequeLines\CompLogo'.</span></span>
10. <span data-ttu-id="28784-164">Włącz opcję „Pokaż szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="28784-164">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="28784-165">Należy zwrócić uwagę, że element komórki formatu „CompLogo” reprezentuje element programu Excel, który jest używany do wypełniania obrazu logo firmy w raporcie.</span><span class="sxs-lookup"><span data-stu-id="28784-165">Note that the ‘CompLogo’ format’s cell element represents the Excel item that is used to populate the company logo image in the report.</span></span> <span data-ttu-id="28784-166">Ten element formatu jest powiązany z elementem modelu danych obrazu, który w czasie wykonywania zawiera obraz logo firmy w formacie binarnym.</span><span class="sxs-lookup"><span data-stu-id="28784-166">This format element is bound to the image data model element that, at runtime, contains a company logo image in binary format.</span></span>   
11. <span data-ttu-id="28784-167">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="28784-167">Click the Mapping tab.</span></span>
12. <span data-ttu-id="28784-168">Kliknij opcję Edycja włączona.</span><span class="sxs-lookup"><span data-stu-id="28784-168">Click Edit enabled.</span></span>
    * <span data-ttu-id="28784-169">Należy zwrócić uwagę, że element komórki formatu „CompLogo” można skonfigurować tak, aby przestał być włączony.</span><span class="sxs-lookup"><span data-stu-id="28784-169">Note that you can make the ‘CompLogo’ format’s cell element so that it’s no longer enabled.</span></span> <span data-ttu-id="28784-170">W takim przypadku skojarzony element obrazu programu Excel będzie ukrywał logo firmy w wygenerowanym raporcie.</span><span class="sxs-lookup"><span data-stu-id="28784-170">In this case, the associated Excel image element will hide a company logo in the generated report.</span></span> <span data-ttu-id="28784-171">Jeśli włączone wyrażenie zwraca wartość TRUE, a zdefiniowane wiązanie nie powoduje zwracania obrazu, skojarzony element obrazu programu Excel wyświetli obraz, który został zapisany w szablonie programu Excel.</span><span class="sxs-lookup"><span data-stu-id="28784-171">If the enabled expression returns TRUE and the defined binding brings no image, the associated Excel image element will show an image that has been saved in the Excel template.</span></span>   
13. <span data-ttu-id="28784-172">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="28784-172">Close the page.</span></span>
14. <span data-ttu-id="28784-173">W drzewie rozwiń węzeł „etykiety: Kontener”.</span><span class="sxs-lookup"><span data-stu-id="28784-173">In the tree, expand 'labels: Container'.</span></span>
    * <span data-ttu-id="28784-174">Niektóre etykiety prezentowane w formularzu czeku z nadrukiem zostaną uwzględnione w raporcie podczas jego tworzenia do celów testowych.</span><span class="sxs-lookup"><span data-stu-id="28784-174">Some labels that are presented in the preprinted cheque form will be included in the report when it’s created for testing purposes.</span></span> <span data-ttu-id="28784-175">Jednak te etykiety nie będą drukowane podczas rzeczywistego drukowania, ponieważ formularz z nadrukiem już je zawiera.</span><span class="sxs-lookup"><span data-stu-id="28784-175">However, those labels won’t be printed during real printing, because the preprinted form already includes them.</span></span>  
15. <span data-ttu-id="28784-176">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="28784-176">Close the page.</span></span>


