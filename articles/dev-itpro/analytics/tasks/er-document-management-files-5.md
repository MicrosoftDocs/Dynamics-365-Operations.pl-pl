--- 
title: "Modyfikowanie i uruchamianie formatu w celu używania plików zarządzania dokumentami w danych wyjściowych formatu"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników)."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.openlocfilehash: b38f69fc169367aa56468b2c8f06b65fd1291c79
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="modify-and-run-format-to-use-document-management-files-in-format-outputs"></a><span data-ttu-id="46ac1-103">Modyfikowanie i uruchamianie formatu w celu używania plików zarządzania dokumentami w danych wyjściowych formatu</span><span class="sxs-lookup"><span data-stu-id="46ac1-103">Modify and run format to use Document Management files in format outputs</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="46ac1-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="46ac1-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="46ac1-105">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="46ac1-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="46ac1-106">W celu wykonania tych kroków należy najpierw wykonać kroki procedury „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 4: Inicjowanie formatu)”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 4): Run format” procedure.</span></span>

<span data-ttu-id="46ac1-107">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="46ac1-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="46ac1-108">Modyfikowanie formatu w celu dodania do generowanych komunikatów treści załączników w formacie binarnym</span><span class="sxs-lookup"><span data-stu-id="46ac1-108">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="46ac1-109">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="46ac1-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="46ac1-110">W drzewie rozwiń węzeł „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-110">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="46ac1-111">W drzewie rozwiń węzeł „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-111">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="46ac1-112">W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)\Przykładowy komunikat faktury elektronicznej”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="46ac1-113">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="46ac1-113">Click Designer.</span></span>
    * <span data-ttu-id="46ac1-114">W generowanych danych wyjściowych wprowadzisz komunikat towarzyszący fakturze jako plik XML z kodowaniem UNICODE.</span><span class="sxs-lookup"><span data-stu-id="46ac1-114">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="46ac1-115">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="46ac1-115">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="46ac1-116">W drzewie zaznacz element „Wspólne\Plik”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-116">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="46ac1-117">W polu Nazwa wpisz „Komunikat Xml”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-117">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="46ac1-118">Komunikat Xml</span><span class="sxs-lookup"><span data-stu-id="46ac1-118">Xml message</span></span>  
9. <span data-ttu-id="46ac1-119">W polu Kodowanie wpisz „UTF-8”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-119">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="46ac1-120">UTF-8</span><span class="sxs-lookup"><span data-stu-id="46ac1-120">UTF-8</span></span>  
10. <span data-ttu-id="46ac1-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="46ac1-121">Click OK.</span></span>
    * <span data-ttu-id="46ac1-122">Skonfiguruj generowanie danych wyjściowych w formacie spakowanego pliku.</span><span class="sxs-lookup"><span data-stu-id="46ac1-122">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="46ac1-123">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="46ac1-123">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="46ac1-124">W drzewie zaznacz element „Wspólne\Folder”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-124">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="46ac1-125">W polu Nazwa wpisz „Dane wyjściowe Zip”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-125">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="46ac1-126">Dane wyjściowe Zip</span><span class="sxs-lookup"><span data-stu-id="46ac1-126">Zip output</span></span>  
14. <span data-ttu-id="46ac1-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="46ac1-127">Click OK.</span></span>
15. <span data-ttu-id="46ac1-128">W drzewie zaznacz element „Dane wyjściowe Zip”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-128">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="46ac1-129">Dodaj załączniki do generowanego pliku zip jako pliki z oryginalnymi nazwami i rozszerzeniami.</span><span class="sxs-lookup"><span data-stu-id="46ac1-129">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="46ac1-130">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="46ac1-130">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="46ac1-131">W drzewie zaznacz element „Wspólne\Plik”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-131">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="46ac1-132">W polu Nazwa wpisz „Załączony plik”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-132">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="46ac1-133">Załączony plik</span><span class="sxs-lookup"><span data-stu-id="46ac1-133">Attached file</span></span>  
19. <span data-ttu-id="46ac1-134">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="46ac1-134">Click OK.</span></span>
20. <span data-ttu-id="46ac1-135">W drzewie zaznacz element „Dane wyjściowe Zip\Załączony plik”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-135">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="46ac1-136">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="46ac1-136">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="46ac1-137">W drzewie zaznacz element „Tekst\Base64”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-137">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="46ac1-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="46ac1-138">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="46ac1-139">Mapowanie elementów nowego formatu na model danych</span><span class="sxs-lookup"><span data-stu-id="46ac1-139">Map new format elements to data model</span></span>
1. <span data-ttu-id="46ac1-140">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="46ac1-140">Click the Mapping tab.</span></span>
2. <span data-ttu-id="46ac1-141">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="46ac1-141">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="46ac1-142">W drzewie rozwiń węzeł „model\Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-142">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="46ac1-143">W drzewie zaznacz element „Dane wyjściowe Zip\Załączony plik\Base64”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-143">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="46ac1-144">W drzewie zaznacz element „model\Załączniki faktur\Zawartość pliku”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-144">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="46ac1-145">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="46ac1-145">Click Bind.</span></span>
7. <span data-ttu-id="46ac1-146">W drzewie zaznacz element „Dane wyjściowe Zip\Załączony plik”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-146">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="46ac1-147">Kliknij opcję Edytuj nazwę pliku.</span><span class="sxs-lookup"><span data-stu-id="46ac1-147">Click Edit filename.</span></span>
9. <span data-ttu-id="46ac1-148">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="46ac1-148">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="46ac1-149">W drzewie rozwiń węzeł „model\Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-149">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="46ac1-150">W drzewie zaznacz element „model\Załączniki faktur\Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-150">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="46ac1-151">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="46ac1-151">Click Add data source.</span></span>
13. <span data-ttu-id="46ac1-152">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="46ac1-152">Click Save.</span></span>
14. <span data-ttu-id="46ac1-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="46ac1-153">Close the page.</span></span>
15. <span data-ttu-id="46ac1-154">W drzewie zaznacz element „model\Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="46ac1-154">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="46ac1-155">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="46ac1-155">Click Bind.</span></span>
17. <span data-ttu-id="46ac1-156">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="46ac1-156">Click Save.</span></span>
18. <span data-ttu-id="46ac1-157">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="46ac1-157">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="46ac1-158">Generowanie zaprojektowanego raportu dla wybranej faktury</span><span class="sxs-lookup"><span data-stu-id="46ac1-158">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="46ac1-159">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="46ac1-159">Click Run.</span></span>
2. <span data-ttu-id="46ac1-160">Rozwiń sekcję Rekordy do uwzględnienia ().</span><span class="sxs-lookup"><span data-stu-id="46ac1-160">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="46ac1-161">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="46ac1-161">Click Filter.</span></span>
4. <span data-ttu-id="46ac1-162">Zaznacz wiersz z arkuszem faktur dla odbiorcy i polem Zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="46ac1-162">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="46ac1-163">W polu kryteriów „Zamówienie sprzedaży” wpisz numer zamówienia 000148.</span><span class="sxs-lookup"><span data-stu-id="46ac1-163">In the Criteria field, In the criteria “Sales order” field, type the order number 000148.</span></span>
    * <span data-ttu-id="46ac1-164">000148</span><span class="sxs-lookup"><span data-stu-id="46ac1-164">000148</span></span>  
6. <span data-ttu-id="46ac1-165">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="46ac1-165">Click OK.</span></span>
7. <span data-ttu-id="46ac1-166">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="46ac1-166">Click OK.</span></span>
    * <span data-ttu-id="46ac1-167">Przejrzyj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="46ac1-167">Review the generated output.</span></span> <span data-ttu-id="46ac1-168">Należy zauważyć, że oprócz komunikatu faktury w formacie XML dla każdego załącznika utworzono również jeden plik.</span><span class="sxs-lookup"><span data-stu-id="46ac1-168">Note, in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="46ac1-169">Pliki załączników są umieszczane w spakowanych danych wyjściowych w formacie binarnym.</span><span class="sxs-lookup"><span data-stu-id="46ac1-169">The attachment files are populated with the zipped output in binary format.</span></span>  


