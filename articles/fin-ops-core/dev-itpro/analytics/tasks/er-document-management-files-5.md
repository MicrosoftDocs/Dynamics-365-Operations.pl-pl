---
title: ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 5 — Modyfikacja i inicjowanie formatu)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego (ER) do używania plików zarządzania dokumentami (załączników) w danych wyjściowych ER. (część 5)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f954b76a09bf7c5edd4c608d400318fbd9386778
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749100"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a><span data-ttu-id="5a655-104">ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 5 — Modyfikacja i inicjowanie formatu)</span><span class="sxs-lookup"><span data-stu-id="5a655-104">ER Use Document Management files in format outputs (Part 5 - Modify and run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5a655-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="5a655-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="5a655-106">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="5a655-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="5a655-107">W celu wykonania tych kroków należy najpierw wykonać kroki procedury „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 4: Uruchamianie formatu)”.</span><span class="sxs-lookup"><span data-stu-id="5a655-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 4: Run format)" procedure.</span></span>

<span data-ttu-id="5a655-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="5a655-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="5a655-109">Modyfikowanie formatu w celu dodania do generowanych komunikatów treści załączników w formacie binarnym</span><span class="sxs-lookup"><span data-stu-id="5a655-109">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="5a655-110">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="5a655-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="5a655-111">W drzewie rozwiń węzeł „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="5a655-111">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="5a655-112">W drzewie rozwiń węzeł „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="5a655-112">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="5a655-113">W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)\Przykładowy komunikat faktury elektronicznej”.</span><span class="sxs-lookup"><span data-stu-id="5a655-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="5a655-114">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="5a655-114">Click Designer.</span></span>
    * <span data-ttu-id="5a655-115">W generowanych danych wyjściowych wprowadzisz komunikat towarzyszący fakturze jako plik XML z kodowaniem UNICODE.</span><span class="sxs-lookup"><span data-stu-id="5a655-115">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="5a655-116">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="5a655-116">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="5a655-117">W drzewie zaznacz element „Wspólne\Plik”.</span><span class="sxs-lookup"><span data-stu-id="5a655-117">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="5a655-118">W polu Nazwa wpisz „Komunikat Xml”.</span><span class="sxs-lookup"><span data-stu-id="5a655-118">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="5a655-119">Komunikat Xml</span><span class="sxs-lookup"><span data-stu-id="5a655-119">Xml message</span></span>  
9. <span data-ttu-id="5a655-120">W polu Kodowanie wpisz „UTF-8”.</span><span class="sxs-lookup"><span data-stu-id="5a655-120">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="5a655-121">UTF-8</span><span class="sxs-lookup"><span data-stu-id="5a655-121">UTF-8</span></span>  
10. <span data-ttu-id="5a655-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5a655-122">Click OK.</span></span>
    * <span data-ttu-id="5a655-123">Skonfiguruj generowanie danych wyjściowych w formacie spakowanego pliku.</span><span class="sxs-lookup"><span data-stu-id="5a655-123">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="5a655-124">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="5a655-124">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="5a655-125">W drzewie zaznacz element „Wspólne\Folder”.</span><span class="sxs-lookup"><span data-stu-id="5a655-125">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="5a655-126">W polu Nazwa wpisz „Dane wyjściowe Zip”.</span><span class="sxs-lookup"><span data-stu-id="5a655-126">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="5a655-127">Dane wyjściowe Zip</span><span class="sxs-lookup"><span data-stu-id="5a655-127">Zip output</span></span>  
14. <span data-ttu-id="5a655-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5a655-128">Click OK.</span></span>
15. <span data-ttu-id="5a655-129">W drzewie zaznacz element „Dane wyjściowe Zip”.</span><span class="sxs-lookup"><span data-stu-id="5a655-129">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="5a655-130">Dodaj załączniki do generowanego pliku zip jako pliki z oryginalnymi nazwami i rozszerzeniami.</span><span class="sxs-lookup"><span data-stu-id="5a655-130">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="5a655-131">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="5a655-131">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="5a655-132">W drzewie zaznacz element „Wspólne\Plik”.</span><span class="sxs-lookup"><span data-stu-id="5a655-132">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="5a655-133">W polu Nazwa wpisz „Załączony plik”.</span><span class="sxs-lookup"><span data-stu-id="5a655-133">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="5a655-134">Załączony plik</span><span class="sxs-lookup"><span data-stu-id="5a655-134">Attached file</span></span>  
19. <span data-ttu-id="5a655-135">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5a655-135">Click OK.</span></span>
20. <span data-ttu-id="5a655-136">W drzewie zaznacz element „Dane wyjściowe Zip\Załączony plik”.</span><span class="sxs-lookup"><span data-stu-id="5a655-136">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="5a655-137">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="5a655-137">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="5a655-138">W drzewie zaznacz element „Tekst\Base64”.</span><span class="sxs-lookup"><span data-stu-id="5a655-138">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="5a655-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5a655-139">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="5a655-140">Mapowanie elementów nowego formatu na model danych</span><span class="sxs-lookup"><span data-stu-id="5a655-140">Map new format elements to data model</span></span>
1. <span data-ttu-id="5a655-141">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="5a655-141">Click the Mapping tab.</span></span>
2. <span data-ttu-id="5a655-142">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="5a655-142">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="5a655-143">W drzewie rozwiń węzeł „model\Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="5a655-143">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="5a655-144">W drzewie zaznacz element „Dane wyjściowe Zip\Załączony plik\Base64”.</span><span class="sxs-lookup"><span data-stu-id="5a655-144">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="5a655-145">W drzewie zaznacz element „model\Załączniki faktur\Zawartość pliku”.</span><span class="sxs-lookup"><span data-stu-id="5a655-145">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="5a655-146">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="5a655-146">Click Bind.</span></span>
7. <span data-ttu-id="5a655-147">W drzewie zaznacz element „Dane wyjściowe Zip\Załączony plik”.</span><span class="sxs-lookup"><span data-stu-id="5a655-147">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="5a655-148">Kliknij opcję Edytuj nazwę pliku.</span><span class="sxs-lookup"><span data-stu-id="5a655-148">Click Edit filename.</span></span>
9. <span data-ttu-id="5a655-149">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="5a655-149">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="5a655-150">W drzewie rozwiń węzeł „model\Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="5a655-150">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="5a655-151">W drzewie zaznacz element „model\Załączniki faktur\Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="5a655-151">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="5a655-152">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="5a655-152">Click Add data source.</span></span>
13. <span data-ttu-id="5a655-153">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="5a655-153">Click Save.</span></span>
14. <span data-ttu-id="5a655-154">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5a655-154">Close the page.</span></span>
15. <span data-ttu-id="5a655-155">W drzewie zaznacz element „model\Załączniki faktur”.</span><span class="sxs-lookup"><span data-stu-id="5a655-155">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="5a655-156">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="5a655-156">Click Bind.</span></span>
17. <span data-ttu-id="5a655-157">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="5a655-157">Click Save.</span></span>
18. <span data-ttu-id="5a655-158">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5a655-158">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="5a655-159">Generowanie zaprojektowanego raportu dla wybranej faktury</span><span class="sxs-lookup"><span data-stu-id="5a655-159">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="5a655-160">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="5a655-160">Click Run.</span></span>
2. <span data-ttu-id="5a655-161">Rozwiń sekcję Rekordy do uwzględnienia ().</span><span class="sxs-lookup"><span data-stu-id="5a655-161">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="5a655-162">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="5a655-162">Click Filter.</span></span>
4. <span data-ttu-id="5a655-163">Zaznacz wiersz z arkuszem faktur dla odbiorcy i polem Zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="5a655-163">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="5a655-164">W polu kryteriów „Zamówienie sprzedaży” wpisz numer zamówienia 000148.</span><span class="sxs-lookup"><span data-stu-id="5a655-164">In the Criteria field, In the criteria "Sales order" field, type the order number 000148.</span></span>
    * <span data-ttu-id="5a655-165">000148</span><span class="sxs-lookup"><span data-stu-id="5a655-165">000148</span></span>  
6. <span data-ttu-id="5a655-166">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5a655-166">Click OK.</span></span>
7. <span data-ttu-id="5a655-167">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5a655-167">Click OK.</span></span>
    * <span data-ttu-id="5a655-168">Przejrzyj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="5a655-168">Review the generated output.</span></span> <span data-ttu-id="5a655-169">Należy zauważyć, że oprócz komunikat faktury w formacie XML dla każdego załącznika utworzono również jeden plik.</span><span class="sxs-lookup"><span data-stu-id="5a655-169">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="5a655-170">Pliki załączników są umieszczane w spakowanych danych wyjściowych w formacie binarnym.</span><span class="sxs-lookup"><span data-stu-id="5a655-170">The attachment files are populated with the zipped output in binary format.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]